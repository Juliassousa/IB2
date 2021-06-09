<template>
  <div>
    <base-header
      class="header pb-8 pt-5 pt-lg-8 d-flex align-items-center"
      style="
        min-height: 600px;
        background-size: cover;
        background-position: center top;
      "
    >
      <!-- Mask -->
      <span class="mask bg-gradient-success opacity-8"></span>
      <!-- Header container -->
      <div class="container">
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
      </div>
      <div class="container-fluid d-flex align-items-center">
        <div class="row">
          <div class="col-lg-7 col-md-10">
            <h1 class="display-2 text-white">Olá, Clark Kent</h1>
            <p class="text-white mt-0 mb-5">
              Essa é sua página de perfil. Aqui você tem acesso ao seu histórico
              e a dados cadastrais.
            </p>
            <a href="#!" class="btn btn-info">Editar Perfil</a>
          </div>
        </div>
      </div>
    </base-header>

    <div class="container-fluid mt--7">
      <div class="row">
        <div class="col-xl-4 order-xl-2 mb-5 mb-xl-0">
          <div class="card card-profile shadow">
            <div class="row justify-content-center">
              <div class="col-lg-3 order-lg-2">
                <div class="card-profile-image">
                  <a href="#">
                    <img
                      src="img/theme/team-4-800x800.jpg"
                      class="rounded-circle"
                    />
                  </a>
                </div>
              </div>
            </div>
            <div
              class="card-header text-center border-0 pt-8 pt-md-4 pb-0 pb-md-4"
            >
              <!-- <div class="d-flex justify-content-between">
                <base-button size="sm" type="info" class="mr-4"
                  >Connect</base-button
                >
                <base-button size="sm" type="default" class="float-right"
                  >Message</base-button
                >
              </div> -->
            </div>
            <div class="card-body pt-0 pt-md-4">
              <div class="row">
                <div class="col">
                  <div
                    class="card-profile-stats d-flex justify-content-center mt-md-5"
                  >
                    <div>
                      <span class="heading">-</span>
                      <span class="description">-</span>
                    </div>
                    <div>
                      <span class="heading">-</span>
                      <span class="description">-</span>
                    </div>
                    <div>
                      <span class="heading">-</span>
                      <span class="description">-</span>
                    </div>
                  </div>
                </div>
              </div>
              <div class="text-center">
                <h3>Clark Kent<span class="font-weight-light">, 33</span></h3>
                <div class="h5 font-weight-300">
                  <i class="ni location_pin mr-2"></i>Pequenópolis, Kansas
                </div>
                <div class="h5 mt-4">
                  <i class="ni business_briefcase-24 mr-2"></i>Solution Manager
                  - Creative Tim Officer
                </div>
                <div>
                  <i class="ni education_hat mr-2"></i>University of Computer
                  Science
                </div>
                <hr class="my-4" />
                <p>
                  Escreva aqui alguma bio para você se divertir eba como estou
                  feliz.
                </p>
              </div>
            </div>
          </div>
        </div>

        <div class="col-xl-8 order-xl-1">
          <card shadow type="secondary">
            <template v-slot:header>
              <div class="bg-white border-0">
                <div class="row align-items-center">
                  <div class="col-8">
                    <h3 class="mb-0">Minha Conta</h3>
                  </div>
                  <div class="col-4 text-right">
                    <a href="#!" class="btn btn-sm btn-primary"
                      >Salvar</a
                    >
                  </div>
                </div>
              </div>
            </template>

            <form>
              <h6 class="heading-small text-muted mb-4">
                Informações do Usuário
              </h6>
              <div class="pl-lg-4">
                <div class="row">
                  <div class="col-lg-6">
                    <base-input
                      alternative=""
                      label="Usuário"
                      placeholder="Usuário"
                      input-classes="form-control-alternative"
                      v-model="model.username"
                    />
                  </div>
                  <div class="col-lg-6">
                    <base-input
                      alternative=""
                      label="E-mail"
                      placeholder="kent@exemplo.com"
                      input-classes="form-control-alternative"
                      v-model="model.email"
                    />
                  </div>
                </div>
                <div class="row">
                  <div class="col-lg-6">
                    <base-input
                      alternative=""
                      label="Nome Completo"
                      placeholder="Nome"
                      input-classes="form-control-alternative"
                      v-model="model.firstName"
                    />
                  </div>
                  <div class="col-lg-6">
                    <base-input
                      alternative=""
                      label="Data de Nascimento"
                      placeholder="14/09/1984"
                      input-classes="form-control-alternative"
                      v-model="model.birthdate"
                    />
                  </div>
                </div>
              </div>
              <hr class="my-4" />
              <!-- Address -->
              <h6 class="heading-small text-muted mb-4">
                Informações de Contato
              </h6>
              <div class="pl-lg-4">
                <div class="row">
                  <div class="col-md-12">
                    <base-input
                      alternative=""
                      label="Endereço"
                      placeholder="Rua dos Bobos, nº0, 4828-5595, Pequenópolis, KA, EUA"
                      input-classes="form-control-alternative"
                      v-model="model.address"
                    />
                  </div>
                </div>
                <div class="row">
                  <div class="col-lg-4">
                    <base-input
                      alternative=""
                      label="Plano de Saúde"
                      placeholder="SUS"
                      input-classes="form-control-alternative"
                      v-model="model.plano"
                    />
                  </div>
                  <div class="col-lg-4">
                    <base-input
                      alternative=""
                      label="Médico Responsável"
                      placeholder="Médico Responsável"
                      input-classes="form-control-alternative"
                      v-model="model.medico"
                    />
                  </div>
                  <div class="col-lg-4">
                    <base-input
                      alternative=""
                      label="Contato de Emergência"
                      placeholder=" Martha Kent (mãe) - (xx)4002-8922"
                      input-classes="form-control-alternative"
                      v-model="model.contato"
                    />
                  </div>
                </div>
              </div>
              <hr class="my-4" />
              <!-- Description -->
              <h6 class="heading-small text-muted mb-4">
                Informações Adicionais
              </h6>
              <div class="pl-lg-4">
                <div class="form-group">
                  <base-input alternative="" label="About Me">
                    <textarea
                      rows="4"
                      class="form-control form-control-alternative"
                      placeholder="Detalhes relevantes ..."
                    >
hum.</textarea
                    >
                  </base-input>
                </div>
              </div>
            </form>
          </card>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "user-profile",
  data() {
    return {
      model: {
        username: "",
        email: "",
        firstName: "",
        birthday: "",
        address: "",
        plano: "",
        medico: "",
        contato: "",
        about: "",
      },
    };
  },
};
</script>
<style></style>
