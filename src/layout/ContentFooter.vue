<template>
  <footer class="footer px-4">
    <div class="row align-items-center justify-content-lg-between">
      <div class="row">
        <div class="col-sm-6 col-md-4">
          <div class="wow fadeInDown" data-wow-delay="0.1s">
            <div class="widget">
              <h5>Sobre o projeto OxiLife</h5>
              <p>
                <small>
                  Projeto criado por estudantes de Engenharia Biomédica da
                  <a href="http://www.ufu.br/"><u>UFU</u></a>
                  na disciplina de Instrumentação Biomédica II.
                </small>
              </p>
            </div>
          </div>
          <div class="wow fadeInDown" data-wow-delay="0.1s">
            <div class="widget">
              <h5>Informações</h5>
              <ul>
                <small>
                  <!-- <li><a href="{% url 'index' %}">Home</a></li> -->
                  <li>
                    <a
                      href="https://github.com/juliassousa/ib2/"
                      target="_blank"
                    >
                      Erros e Sugestões
                    </a>
                  </li>
                  <li>
                    <a
                      href="https://github.com/juliassousa/ib2/LICENSE"
                      target="_blank"
                    >
                      Licença</a
                    >
                  </li>
                </small>
              </ul>
            </div>
          </div>
        </div>
        <div class="col-sm-1 col-md-4">
          <div class="wow fadeInDown" data-wow-delay="0.1s">
            <div class="widget">
              <h5>Contato</h5>
              <li>
                <i class="ni ni-mobile-button"></i>
                <small> +55 34 4002-8922 </small>
              </li>
              <li>
                <i class="ni ni-email-83"></i>
                <small> OxiLife@gmail.com </small>
              </li>
            </div>
          </div>
        </div>
        <div class="col-sm-6 col-md-4">
          <div class="wow fadeInDown" data-wow-delay="0.1s">
            <div class="widget">
              <h5>Localização</h5>
              <p>
                <small>
                  Av. João Naves de Ávila, 2121 - Santa Mônica, Uberlândia - MG,
                  38408-014
                </small>
              </p>
            </div>
          </div>
          <!-- <div class="wow fadeInDown" data-wow-delay="0.1s">
            <div class="widget">
              <h5>Redes Sociais</h5>
              <ul class="company-social">
                <li>
                  <a href="https://github.com/juliassousa/ib2/"
                    ><i class="ni ni-github"></i
                  ></a>
                </li>
                <li class="social-dribble">
                  <a href="https://www.youtube.com/watch?v=dQw4w9WgXcQ">
                  <i class="fa fa-youtube"></i>
                  </a>
                </li>
              </ul>
            </div>
          </div> -->
        </div>
      </div>
    </div>
    <!-- <div class="sub-footer">
      <div class="container">
        <div class="row">
          <div class="col-sm-6 col-md-6 col-lg-6">
            <div class="wow fadeInLeft" data-wow-delay="0.1s">
              <div class="text-left">
                <p>&copy;Copyright</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div> -->
  </footer>
  <!-- <footer class="footer px-4">
    <div class="row align-items-center justify-content-lg-between">
      <div class="col-lg-6">
        <div class="copyright text-center text-lg-left text-muted">
          © {{ year }}
          <a
            href="https://www.creative-tim.com"
            class="font-weight-bold ml-1"
            target="_blank"
            >OxiLife</a
          >
        </div>
      </div>
      <div class="col-lg-6">
        <ul
          class="nav nav-footer justify-content-center justify-content-lg-end"
        >
          <li class="nav-item">
            <a
              href="https://www.creative-tim.com"
              class="nav-link"
              target="_blank"
              >OxiLife</a
            >
          </li>
          <li class="nav-item">
            <a
              href="https://www.creative-tim.com/presentation"
              class="nav-link"
              target="_blank"
              >Sobre nós</a
            >
          </li>
          <li class="nav-item">
            <a
              href="https://www.creative-tim.com/blog"
              class="nav-link"
              target="_blank"
              >Blog</a
            >
          </li>
          <li class="nav-item">
            <a
              href="https://www.creative-tim.com/license"
              class="nav-link"
              target="_blank"
              >Licença</a
            >
          </li>
        </ul>
      </div>
    </div>
  </footer> -->
</template>
<script>
export default {
  data() {
    return {
      year: new Date().getFullYear(),
    };
  },
};
</script>
<style></style>
