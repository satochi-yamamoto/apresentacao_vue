<template>
  <div>
    <!-- Header -->
    <header class="header">
      <div class="container header-flex">
        <nav class="navbar" :class="{ active: isMenuOpen }">
          <ul>
            <li><a href="#about">Sobre</a></li>
            <li><a href="#experience">Experiência</a></li>
            <li><a href="#education">Formação</a></li>
            <li><a href="#skills">Habilidades</a></li>
            <li><a href="#contact">Contato</a></li>
          </ul>
        </nav>
        <div class="header-icons">
          <a href="https://github.com/satochi-yamamoto" target="_blank" rel="noopener noreferrer" title="GitHub">
            <font-awesome-icon :icon="['fab', 'github']" />
          </a>
          <a href="https://www.linkedin.com/in/alexyamamoto/" target="_blank" rel="noopener noreferrer" title="LinkedIn">
            <font-awesome-icon :icon="['fab', 'linkedin']" />
          </a>
          <a href="#" target="_blank" rel="noopener noreferrer" title="Discord">
            <font-awesome-icon :icon="['fab', 'discord']" />
          </a>
        </div>
        <div class="mobile-menu" @click="toggleMenu">
          <font-awesome-icon :icon="['fas', 'bars']" />
        </div>
      </div>
    </header>

    <!-- Hero Section -->
    <section class="hero">
      <div class="container hero-container">
        <div class="hero-content">
          <h1>Alexandre Satochi Yamamoto</h1>
          <h2>Coordenador de Desenvolvimento de Software e TI,</h2>
          <p>+25 anos de atuação na área de TI dos quais 12 anos dedicado a liderança de equipes em projetos de TI e de Desenvolvimento de Softwares</p>
          <div class="hero-cta">
            <a href="#contact" class="btn btn-primary">Entre em Contato</a>
            <a href="#experience" class="btn btn-outline">Ver Experiência</a>
          </div>
        </div>
        <div class="hero-image">
          <img src="images/avatar.jpg" alt="Alexandre Satochi Yamamoto">
        </div>
      </div>
    </section>

    <!-- About Section -->
    <section id="about" class="section about">
      <div class="container">
        <h2 class="section-title">Sobre Mim</h2>
        <div class="about-content">
          <p>Profissional com mais de 25 anos de atuação na área de TI, especializado em gestão de equipes, infraestrutura de TI, desenvolvimento de software e segurança da informação. Possuo vasta experiência em projetos de modernização tecnológica, eficiência operacional da equipe de TI e redução de custos, com amplo domínio em metodologias ágeis, DevOps e padrões de segurança (ISO 9001, ISO 27001). Minha expertise inclui implantação de sistemas, gestão de servidores, banco de dados (SQL Server, MySQL) e plataformas de nuvem. Sou focado na entrega de valor ao negócio por meio de gestão de projetos e coordenação de equipes.</p>
          <p>Formado em Gestão da Tecnologia da Informação e Pos Graduado em Engenharia de Software possuo varios cursos de especialização na área.</p>
          <div class="about-stats">
            <div class="stat-item">
              <span class="stat-number">25+</span>
              <span class="stat-text">Anos de Experiência</span>
            </div>
            <div class="stat-item">
              <span class="stat-number">12+</span>
              <span class="stat-text">Anos de liderança de equipes</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Experience Section -->
    <section id="experience" class="section experience">
      <div class="container">
        <h2 class="section-title">Experiência Profissional</h2>
        <div class="timeline">
          <ExperienceItem
            v-for="(exp, i) in experiences"
            :key="i"
            :date="exp.date"
            :company="exp.company"
            :role="exp.role"
            :desc="exp.desc"
            :odd="i % 2 === 0"
          />
        </div>
      </div>
    </section>

    <!-- Education Section -->
    <section id="education" class="section education">
      <div class="container">
        <h2 class="section-title">Formação Acadêmica</h2>
        <div class="education-grid">
          <EducationItem
            v-for="(edu, i) in education"
            :key="i"
            :school="edu.school"
            :course="edu.course"
            :desc="edu.desc"
            :last="i === education.length - 1"
          />
        </div>
      </div>
    </section>

    <!-- Skills Section -->
    <section id="skills" class="section skills">
      <div class="container">
        <h2 class="section-title">Habilidades</h2>
        <div class="skills-grid">
          <SkillBar v-for="(skill, i) in skills" :key="i" :name="skill.name" :level="skill.level" />
        </div>
      </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="section projects">
      <div class="container">
        <h2 class="section-title">Projetos Destacados</h2>
        <div class="projects-grid">
          <ProjectCard
            v-for="(project, i) in projects"
            :key="i"
            :img="project.img"
            :title="project.title"
            :desc="project.desc"
            :link="project.link"
          />
        </div>
      </div>
    </section>

    <!-- Trabalho voluntário-->
    <section id="volunteer" class="section volunteer">
      <div class="container">
        <h2 class="section-title">Trabalho Voluntário</h2>
        <div
          class="volunteer-content"
          v-for="(vol, i) in volunteer"
          :key="i"
        >
          <h3>{{ vol.title }}</h3>
          <p>{{ vol.desc }}</p>
        </div>
      </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="section contact">
      <div class="container">
        <h2 class="section-title">Entre em Contato</h2>
        <div class="contact-content">
          <div class="contact-info">
            <div class="info-item">
              <font-awesome-icon :icon="['fas', 'envelope']" />
              <span>yamamoto@ydsoftware.com.br</span>
            </div>
            <div class="info-item">
              <font-awesome-icon :icon="['fab', 'linkedin']" />
              <span>linkedin.com/in/alexyamamoto</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <footer class="footer">
      <div class="container">
        <div class="footer-content">
          <div class="footer-logo">
            <a href="#">Alexandre Satochi Yamamoto</a>
          </div>
          <div class="footer-links">
            <ul>
              <li><a href="#about">Sobre</a></li>
              <li><a href="#experience">Experiência</a></li>
              <li><a href="#contact">Contato</a></li>
            </ul>
          </div>
        </div>
        <div class="footer-copyright">
          <p>&copy; {{ currentYear }} Alexandre Satochi Yamamoto. Todos os direitos reservados.</p>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
import { ref } from 'vue';
import { library } from '@fortawesome/fontawesome-svg-core';
import { faGithub, faLinkedin, faDiscord } from '@fortawesome/free-brands-svg-icons';
import { faGraduationCap, faEnvelope, faBars } from '@fortawesome/free-solid-svg-icons';
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';

library.add(faGithub, faLinkedin, faDiscord, faGraduationCap, faEnvelope, faBars);

const experiences = [
  {
    date: '2025 - Presente',
    company: 'Adelco Sistema de Energia',
    role: 'Coodenador de TI',
    desc: 'Liderança de equipes multidisciplinares no desenvolvimento do ERP Protheus da TOTVS.'
  },
  {
    date: '2024 - 2025',
    company: 'Terra Nova Logistica',
    role: 'Coordenador de TI',
    desc: 'Gestão da área de TI, responsavel pela equipe de Infraestrutura, Desenvolvimento e BI '
  },
  {
    date: '2023 - 2024',
    company: 'Primi Tecnologia',
    role: 'Coodenador de Desenvolvimento',
    desc: 'Responsagel pela gestão da equipe de desenvolvimento, liderando no desenvolvimento de aplicações internas e Mobiles, Gestão de equipe, onde implementei o DEVOps e a metodologia Agile'
  },
  {
    date: '2020 - 2023',
    company: 'K2A Partners',
    role: 'Coordenador de TI e Operações',
    desc: 'liderei a infraestrutura de TI, gerenciando serviços e servidores em ambientes de nuvem, garantindo links eficazes, acesso seguro via VPN e supervisionando as redes e serviços de TI. Como mantenedor de sistemas e DBA, desenvolvi novos relacionamentos de dados e criei procedimentos para a equipe de desenvolvimento, além de integrar dados com o Power BI.'
  },
  {
    date: '2016 - 2020',
    company: 'Atiks',
    role: 'Coordenador de Operações e Desenvolvimento de Software',
    desc: 'Na liderança de Projetos Técnicos na Atiks TEM, fui encarregado de liderar e gerenciar diversas iniciativas estratégicas, desempenhando funções cruciais que incluíram gerenciamento de DevOps, supervisão do ciclo de vida dos projetos e validação de novas versões. Colaborei com a equipe de operações para garantir o desenvolvimento de novos itens e módulos para o Sistema TEM. Liderei com sucesso um projeto crucial de conversão de leitura OCR de faturas, melhorando significativamente a eficiência dos processos..'
  },
  {
    date: '2011 - 2015',
    company: 'TST Telmax',
    role: 'Coordenador de TI',
    desc: 'Na TST Telmax Soluções em Telecomunicações, atuei como Coordenador de Infraestrutura de TI, desempenhando um papel fundamental na gestão e desenvolvimento da infraestrutura de tecnologia da informação. Minhas principais responsabilidades incluíram liderar uma equipe de TI, gerenciar projetos de TI desde o planejamento até a implementação, integrar operações entre matriz e filiais, supervisionar intranet, backup, servidores em nuvem, administrar redes, servidores, telefonia e aplicações internas, iniciar projeto de telefonia SIP, contribuir para o desenvolvimento de sistemas e aplicativos de gestão de projetos, e auxiliar na integração de políticas ISO e no desenvolvimento de ferramentas de gestão de TI..'
  },
  {
    date: '2005 - 2011',
    company: 'Motorola Industrial',
    role: 'Coordenador de Campo',
    desc: 'Na Motorola Mobility, atuei como Coordenador Field Test, desempenhando um papel fundamental no campo de testes de aparelhos celulares. Minhas principais responsabilidades e competências incluíram:\n\nCoordenação e Gerenciamento de Equipes de Testes de Aparelhos Celulares: Liderei e gerenciei equipes de testes de aparelhos celulares, garantindo a eficácia e qualidade dos testes.\n\nControle de Qualidade e Ações de Qualidade na América Latina: Atuei na coordenação e controle de qualidade dos testes e ações de qualidade em toda a América Latina.\n\nDesenvolvimento e Implementação de Ferramentas e Softwares de Testes para Telefones Celulares: Contribuí para o desenvolvimento e implementação de ferramentas e softwares de testes para telefones celulares..'
  }
];

const education = [
  {
    school: 'FMU',
    course: 'Engenharia de Software',
    desc: 'Pos Graduação em Curso'
  },
  {
    school: 'UNISA - Universidade Santo Amaro',
    course: 'Gestão da Tecnologia da Informação',
    desc: 'Graduação completa'
  },
  {
    school: 'FESP - Faculdade de engenharia São Paulo',
    course: 'Engenharia Eletrica',
    desc: 'Graduação incompleta'
  }
];

const skills = [
  { name: 'Gestão de Projetos', level: 90 },
  { name: 'AWS', level: 90 },
  { name: 'Microsoft Azure', level: 100 },
  { name: 'Oracle Cloud', level: 90 },
  { name: 'ISO 9001 / ISO 27001', level: 90 },
  { name: 'Docker', level: 100 },
  { name: 'Metodologia Agil', level: 100 },
  { name: 'CI / CD', level: 100 },
  { name: 'SQL-Server', level: 100 },
  { name: 'MYSQL', level: 100 },
  { name: 'PostgreSQL', level: 100 },
  { name: 'Python / Django', level: 100 },
  { name: 'PHP / Laravel', level: 100 },
  { name: 'Node-js', level: 100 },
  { name: 'Java Script', level: 100 },
  { name: 'Power BI', level: 100 }
];

const projects = [
  {
    img: 'images/projects/project1.jpg',
    title: 'Site de apresentação versão React.js',
    desc: 'Site de apresentação desenvolvido na linguagem React',
    link: 'https://react.satochi.com.br/'
  },
  {
    img: 'images/projects/project2.jpg',
    title: 'Site de apresentação versão Vue.js',
    desc: 'Site de apresentação desenvolvido na linguagem Vue3',
    link: 'https://vue.satochi.com.br/'
  },
  {
    img: 'images/projects/whats.jpg',
    title: 'API Automação Whatsapp',
    desc: 'API de Automação de mensagens do Whatsapp',
    link: '#'
  }
];

const volunteer = [
  {
    title: 'Grupo Escoteiro Cooper Cotia - 131',
    desc: 'Atualmente atuo como voluntário na Escoteira do Cooper Cotia do Distrito do Butantã SP, realizo trabalhos na equipe de apoio de Pais, atuando como suporte nas atividades, refeições e em Festas dos jovens do grupo Escoteiro aos finais de semana.'
  },
  {
    title: 'Representante do GAP - CooperAtletico Clube',
    desc: 'Atuante no Grupo de apoio a prevenção realizando monitorias e inspeções do Clube CooperCotia em busca de melhorias e qualidade para os Socios.'
  }
];

export default {
  name: 'App',
  components: {
    FontAwesomeIcon,
    ExperienceItem: {
      props: ['date', 'company', 'role', 'desc', 'odd'],
      template: `
        <div class="timeline-item">
          <div class="timeline-date">{{ date }}</div>
          <div class="timeline-content" :style="odd ? 'margin-left:54%' : 'margin-right:54%'">
            <h3>{{ company }}</h3>
            <h4>{{ role }}</h4>
            <p style="white-space:pre-line">{{ desc }}</p>
          </div>
        </div>
      `
    },
    EducationItem: {
      props: ['school', 'course', 'desc', 'last'],
      template: `
        <div class="education-item" :style="last ? 'border-bottom:none;padding-bottom:0;' : ''">
          <div class="education-icon">
            <font-awesome-icon :icon="['fas', 'graduation-cap']" />
          </div>
          <div>
            <h3>{{ school }}</h3>
            <h4>{{ course }}</h4>
            <p>{{ desc }}</p>
          </div>
        </div>
      `
    },
    SkillBar: {
      props: ['name', 'level'],
      template: `
        <div class="skill-item">
          <h3>{{ name }}</h3>
          <div class="skill-bar">
            <div class="skill-level" :style="'width:' + level + '%'"></div>
          </div>
        </div>
      `
    },
    ProjectCard: {
      props: ['img', 'title', 'desc', 'link'],
      template: `
        <div class="project-item">
          <img :src="img" :alt="title">
          <div class="project-overlay">
            <h3>{{ title }}</h3>
            <p>{{ desc }}</p>
            <a :href="link" class="btn btn-outline" target="_blank" rel="noopener">Ver Detalhes</a>
          </div>
        </div>
      `
    }
  },
  setup() {
    const currentYear = ref(new Date().getFullYear());
    const isMenuOpen = ref(false);

    const toggleMenu = () => {
      isMenuOpen.value = !isMenuOpen.value;
    };

    return {
      currentYear,
      isMenuOpen,
      toggleMenu,
      experiences,
      education,
      skills,
      projects,
      volunteer
    };
  }
};
</script>

<style scoped>
/* ... (mantém o CSS original, remova o style inline dos itens) ... */
.projects-grid {
  display: flex;
  gap: 32px;
  flex-wrap: wrap;
}
.project-item {
  flex: 1 1 300px;
  min-width: 280px;
  max-width: 350px;
  position: relative;
}
.project-item img {
  width: 100%;
  border-radius: 8px;
}
.project-overlay {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  background: rgba(0,0,0,0.7);
  color: #fff;
  padding: 16px;
  border-radius: 0 0 8px 8px;
  opacity: 0;
  transition: opacity 0.3s;
}
.project-item:hover .project-overlay {
  opacity: 1;
}
.volunteer-content {
  margin-bottom: 32px;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}
.hero-container {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
@media (max-width: 768px) {
  .projects-grid {
    flex-direction: column;
    gap: 16px;
  }
  .hero-container {
    flex-direction: column;
  }
}
</style>
