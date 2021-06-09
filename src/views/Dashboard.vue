<template>
  <div>
    <base-header type="gradient-success" class="pb-6 pb-8 pt-5 pt-md-8">
      <div class="header-body text-center mb-7">
        <div class="row justify-content-center">
          <div class="col-lg-5 col-md-6">
            <img
              src="img/brand/green.png"
              alt="image"
              height="101"
              width="216"
            />
          </div>
        </div>
      </div>
      <div class="botões">
        <base-button type="primary" class="my-4">Iniciar Coleta</base-button>
        <base-button type="primary" class="my-4">Parar Coleta</base-button>
        <!--  <button v-on:click="cliquei_no_button_para_carregar_os_dados">
          Iniciar Coleta
        </button>
        <button v-on:click="counter += 1">Add 1</button>
        <p style="color: red; background: yellow">
          The button above has been clicked {{ counter }} times.
        </p> -->
      </div>
      <div class="row">
        <div class="col-xl-3 col-lg-6">
          <stats-card
            title="Frequência cardíaca"
            type="gradient-red"
            v-model:sub-title="bpm"
            icon="fa fa-heart"
            class="mb-4 mb-xl-0"
          >
            <!-- <template v-slot:footer>
              <span class="text-success mr-2">
                <i class="fa fa-arrow-up"></i> 3.48%
              </span>
              <span class="text-nowrap">Since last month</span>
            </template> -->
          </stats-card>
        </div>
        <div class="col-xl-3 col-lg-6">
          <stats-card
            title="SPO2"
            type="gradient-orange"
            v-model:sub-title="spo2"
            icon="ni ni-sound-wave"
            class="mb-4 mb-xl-0"
          >
            <!-- <template v-slot:footer>
              <span class="text-success mr-2">
                <i class="fa fa-arrow-up"></i> 12.18%
              </span>
              <span class="text-nowrap">Since last month</span>
            </template> -->
          </stats-card>
        </div>
        <div class="col-xl-3 col-lg-6">
          <stats-card
            title="Temperatura"
            type="gradient-green"
            v-model:sub-title="temperatura"
            icon="fa fa-thermometer"
            class="mb-4 mb-xl-0"
          >
            <!-- <template v-slot:footer>
              <span class="text-danger mr-2">
                <i class="fa fa-arrow-down"></i> 5.72%
              </span>
              <span class="text-nowrap">Since last month</span>
            </template> -->
          </stats-card>
        </div>
        <div class="col-xl-3 col-lg-6">
         <!--  <stats-card
            title="Ajuda no Diagnóstico"
            type="gradient-info"
            v-model:sub-title="diagnostico"
            icon="fa fa-thumbs-up"
            class="mb-4 mb-xl-0"
          >
             <template v-slot:footer>
              <span class="text-success mr-2">
                <i class="fa fa-arrow-up"></i> 54.8%
              </span>
              <span class="text-nowrap">Since last month</span>
            </template>
          </stats-card> -->
        </div>
      </div>
    </base-header>

    <div class="container-fluid mt--7">
      <!--Charts-->
      <div class="row" style="/*display: none;*/">
        <div class="col-xl-8 mb-5 mb-xl-0">
          <card type="default" header-classes="bg-transparent">
            <template v-slot:header>
              <div class="row align-items-center">
                <div class="col">
                  <h5 class="h3 text-white mb-0">Oxigenação sanguínea</h5>
                </div>
                <div class="col">
                  <ul class="nav nav-pills justify-content-end">
                    <!-- <li class="nav-item mr-2 mr-md-0">
                      <a
                        class="nav-link py-2 px-3"
                        href="#"
                        :class="{ active: bigLineChart.activeIndex === 0 }"
                        @click.prevent="initBigChart(0)"
                      >
                        <span class="d-none d-md-block">Month</span>
                        <span class="d-md-none">M</span>
                      </a>
                    </li> -->
                    <!-- <li class="nav-item">
                      <a
                        class="nav-link py-2 px-3"
                        href="#"
                        :class="{ active: bigLineChart.activeIndex === 1 }"
                        @click.prevent="initBigChart(1)"
                      >
                        <span class="d-none d-md-block">Week</span>
                        <span class="d-md-none">W</span>
                      </a>
                    </li> -->
                  </ul>
                </div>
              </div>
            </template>
            <div class="chart-area">
              <canvas :height="350" :id="salesChartID"></canvas>
            </div>
          </card>
        </div>

        <!-- <div class="col-xl-4">
          <card header-classes="bg-transparent">
            <template v-slot:header>
              <div class="row align-items-center">
                <div class="col">
                  <h6 class="text-uppercase text-muted ls-1 mb-1">
                    Performance
                  </h6>
                  <h5 class="h3 mb-0">Total orders</h5>
                </div>
              </div>
            </template>
            <div class="chart-area">
              <canvas :height="350" :id="ordersChartID"></canvas>
            </div>
          </card>
        </div>-->
      </div>

      <!-- End charts-->

      <!--Tables-->
      <!--  <div class="row mt-5">
        <div class="col-xl-8 mb-5 mb-xl-0">
          <page-visits-table></page-visits-table>
        </div>
        <div class="col-xl-4">
          <social-traffic-table></social-traffic-table>
        </div>
      </div> -->
      <!--End tables-->
    </div>
  </div>
</template>
<script>
// Charts
/* import { ordersChart } from "@/components/Charts/Chart"; */
import Chart from "chart.js";

/* import PageVisitsTable from "./Dashboard/PageVisitsTable";
import SocialTrafficTable from "./Dashboard/SocialTrafficTable"; */
let chart;

export default {
  /* components: {
    PageVisitsTable,
    SocialTrafficTable,
  }, */
  data() {
    return {
      spo2: "95%",
      bpm: "70 bpm",
      temperatura: "38.5 ºC",
      diagnostico: "Febre",
      valores_grafico: ["50", "61", "32"], //coloca aqui vazio e qnd chamar o arduino vai enchendo
      counter: 0,
      salesChartID: "salesChart",
      /*  ordersChartID: "ordersChart", */
      bigLineChart: {
        allData: [
          [0, 20, 5, 25, 10, 30, 15, 40, 40],
          [0, 45, 80, 105, 115, 100, 50, 60, 70],
        ],
        activeIndex: 0,
      },
    };
  },
  methods: {
    cliquei_no_button_para_carregar_os_dados() {
      // alert("heelllo");
      // Adicionar numero aletorio ou chamada pra obter os dados da ESP
      this.spo2 = "98%";
      this.bpm = "60 bpm";
      this.temperatura = "40.9 ºC";
      this.diagnostico = "Morreu";
      this.getArduinoData();
    },
    getArduinoData() {
      //Fetch the data from api
      // Dados do arduino
      // TODO: Trocar pelo link do arduino na ESP
      // Esse link quem define é quem fizer o código da ESP
      // Fala pra ela retonar um JSON com os dados já processados
      /*
      Exemplo de retorno em JSON: (mas pode ser outro formato se quiser sei la)
      {
        'spo2': blabla,
        'bpm': blabla,
        'temperatura': blabla,
        'diagnostico': blabla
      }
      */
      /*
      fetch("http://localhost:8000/api/dadosdapessoa/", {
        method: "GET",
        headers: {
          'Authorization': "Token 7832b484027e35223b8bdfcadf0b8f3e19b60d48",
        }
      }).then(
        response => response.json()
      ).then(
        response => {
          this.spo2 = response.spo2;
          this.bpm = response.bpm;
          this.temperatura = response.temperatura;
          this.diagnostico = response.diagnostico;
          // Pesquisar como ir adionando varios numa lista em vue
          this.valores_grafico.adicionar_valor(response.valor_grafico)
          this.funcao_que_chama_para_mandar_o_valor_pro_grafico()
      }).catch(
        error => alert(error)
      );
      */
      /*
      fetch("http://localhost:8000/api/dadosdapessoa/", {
        method: "GET",
        headers: {
          'Authorization': "Token 7832b484027e35223b8bdfcadf0b8f3e19b60d48",
        }
      }).then(
        response => response.json()
      ).then(
        response => {
          this.reagentes = response;
      }).catch(
        error => {
          this.spo2 = "98%";
          this.bpm = "60 bpm";
          this.temperatura = "40.9 ºC";
          this.diagnostico = "Morreu";
        }
      );
      */
    },
    initBigChart(index) {
      chart.destroy();
      chart = new Chart(
        document.getElementById(this.salesChartID).getContext("2d"),
        {
          type: "line",
          data: {
            labels: ["May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"],
            datasets: [
              {
                label: "Performance",
                tension: 0.4,
                borderWidth: 4,
                borderColor: "#5e72e4",
                pointRadius: 0,
                backgroundColor: "transparent",
                data: this.bigLineChart.allData[index],
              },
            ],
          },
          options: {
            responsive: true,
            maintainAspectRatio: false,
            legend: {
              display: false,
            },
            tooltips: {
              enabled: true,
              mode: "index",
              intersect: false,
            },
            scales: {
              yAxes: [
                {
                  barPercentage: 1.6,
                  gridLines: {
                    drawBorder: false,
                    color: "rgba(29,140,248,0.0)",
                    zeroLineColor: "transparent",
                  },
                  ticks: {
                    padding: 0,
                    fontColor: "#8898aa",
                    fontSize: 13,
                    fontFamily: "Open Sans",
                  },
                },
              ],
              xAxes: [
                {
                  barPercentage: 1.6,
                  gridLines: {
                    drawBorder: false,
                    color: "rgba(29,140,248,0.0)",
                    zeroLineColor: "transparent",
                  },
                  ticks: {
                    padding: 10,
                    fontColor: "#8898aa",
                    fontSize: 13,
                    fontFamily: "Open Sans",
                  },
                },
              ],
            },
            layout: {
              padding: 0,
            },
          },
        }
      );
      this.bigLineChart.activeIndex = index;
    },
  },
  mounted() {
    chart = new Chart(
      document.getElementById(this.salesChartID).getContext("2d"),
      {
        type: "line",
        data: {
          labels: ["May", "Jun", "Jul", "Aug", "Sep", "Oct", "Nov", "Dec"],
          datasets: [
            {
              label: "Performance",
              tension: 0.4,
              borderWidth: 4,
              borderColor: "#5e72e4",
              pointRadius: 0,
              backgroundColor: "transparent",
              data: this.bigLineChart.allData[1],
            },
          ],
        },
        options: {
          responsive: true,
          maintainAspectRatio: false,
          legend: {
            display: false,
          },
          tooltips: {
            enabled: true,
            mode: "index",
            intersect: false,
          },
          scales: {
            yAxes: [
              {
                barPercentage: 1.6,
                gridLines: {
                  drawBorder: false,
                  color: "rgba(29,140,248,0.0)",
                  zeroLineColor: "transparent",
                },
                ticks: {
                  padding: 0,
                  fontColor: "#8898aa",
                  fontSize: 13,
                  fontFamily: "Open Sans",
                },
              },
            ],
            xAxes: [
              {
                barPercentage: 1.6,
                gridLines: {
                  drawBorder: false,
                  color: "rgba(29,140,248,0.0)",
                  zeroLineColor: "transparent",
                },
                ticks: {
                  padding: 10,
                  fontColor: "#8898aa",
                  fontSize: 13,
                  fontFamily: "Open Sans",
                },
              },
            ],
          },
          layout: {
            padding: 0,
          },
        },
      }
    );
    /* ordersChart.createChart(this.ordersChartID); */
  },
};
</script>
<style></style>
