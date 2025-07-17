<style>
  .responsive-iframe-container {
    position: relative;
    width: 100%;
    max-width: 1200px; /* Ограничение максимальной ширины */
    margin: 0 auto; /* Центрирование */
    overflow: hidden; /* Убираем лишние полосы прокрутки */
  }

  .responsive-iframe {
    width: 100%;
    border: none;
    /* Начальная высота, которая будет переопределена JavaScript */
    height: 600px;
  }

  /* Адаптация для меньших экранов */
  @media screen and (max-width: 768px) {
    .responsive-iframe {
      height: 500px; /* Меньшая высота для планшетов */
    }
  }

  @media screen and (max-width: 480px) {
    .responsive-iframe {
      height: 400px; /* Еще меньшая высота для мобильных */
    }
  }
</style>

<div class="responsive-iframe-container">
  <iframe class="responsive-iframe" src="https://docs.google.com/spreadsheets/d/e/2PACX-1vRrtNsVjDH35c4vGbh-L5G8q1T6LQJIRaDM-vdNU22a6o6xBXm1C8jEspzfskYbDolx6ZWNki5eLaLa/pubhtml?widget=true&headers=false"></iframe>
</div>

<script>
  function adjustIframeHeight() {
    const iframe = document.querySelector('.responsive-iframe');
    // Устанавливаем высоту iframe на основе его содержимого
    iframe.style.height = '600px'; // Начальная высота

    // Проверяем, если содержимое загружено
    iframe.addEventListener('load', () => {
      try {
        const contentHeight = iframe.contentWindow.document.body.scrollHeight;
        iframe.style.height = `${contentHeight}px`;
      } catch (e) {
        console.warn('Не удалось получить высоту содержимого iframe:', e);
      }
    });
  }

  // Вызываем функцию при загрузке страницы и при изменении размера окна
  window.addEventListener('load', adjustIframeHeight);
  window.addEventListener('resize', adjustIframeHeight);
</script>
