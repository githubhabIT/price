<style>
  .responsive-iframe {
    width: 90vw; /* 90% ширины окна */
    height: 80vh; /* 80% высоты окна */
    max-width: 1000px;
    border: none;
  }

  @media screen and (max-width: 768px) {
    .responsive-iframe {
      height: 60vh; /* Уменьшенная высота для планшетов */
    }
  }

  @media screen and (max-width: 480px) {
    .responsive-iframe {
      height: 50vh; /* Еще меньшая высота для мобильных */
    }
  }
</style>

<iframe class="responsive-iframe" src="https://docs.google.com/spreadsheets/d/e/2PACX-1vRrtNsVjDH35c4vGbh-L5G8q1T6LQJIRaDM-vdNU22a6o6xBXm1C8jEspzfskYbDolx6ZWNki5eLaLa/pubhtml?widget=true&headers=false"></iframe>
