<template>
  <div class="top">
    <section class="user">
      <div class="user__avatar">
        <img class="user__img" src="@/assets/images/user.png" alt="avatar img" />
      </div>
      <div class="user__info">
        <h1 class="user__name">Eva Jonson</h1>
        <div class="user__position">Sales Manager</div>
        <div class="user__description">
            I will find the best offers for you.  My services are absolutely free.
        </div>
      </div>
    </section>

    <section class="services">
      <div class="services__name">Services</div>

      <ul class="services__progress">
        <li class="services__progress-a">
          <span class="services__progress-text">Manual tour booking</span>
          <span class="services__progress-count">11</span>
        </li>
        <li class="services__progress-b">
          <span class="services__progress-text">Package tours</span>
          <span class="services__progress-count">3</span>
        </li>
        <li class="services__progress-c">
          <span class="services__progress-text">Hotels</span>
          <span class="services__progress-count">1</span>
        </li>
      </ul>

      <div class="services__total">
        <div class="services__total-text">Total</div>
        <span class="services__total-count">15</span>
      </div>
    </section>
  </div>
</template>

<style lang="scss" scoped>
@import '../assets/styles/mixins';
.user {
  display: flex;
  padding-top: 15px;

  &__avatar {
    margin: 0;
    padding: 0;
    z-index: 1;
  }
  &__img {
    border-radius: 100px;
    max-height: 124px;
    max-width: 124px;
  }
  &__info {
    padding: 5px 10px;
    width: 100%;

    @include phone {
    padding: 2px 2px;
    }
  }

  &__name {
    font-size: 16px;
    line-height: 20px;
    color: #333;
  }

  &__position {
    font-size: 12px;
    line-height: 20px;
    color: #808080;
    margin-top: 2px;
  }

  &__description {
    font-size: 14px;
    line-height: 20px;
    background-color: #fffbc8;
    border: 1px solid #dadada;
    border-radius: 5px;
    box-sizing: border-box;
    margin-top: 5px;
    padding: 10px 20px 10px 45px;
    width: calc(100% + 45px);
    z-index: 0;
    float: right;

    @include phone {
    padding: 5px 12px 5px 45px;
    }
  }

}
.services {
  padding-left: 135px;
  margin-bottom: 10px;
  font-size: 13px;

  @include phone {
    padding-left: 0;
  }

  &__name {
    padding-right: 24px;
    margin-bottom: 8px;
    text-align: right;
    line-height: 1.1;
  }

  &__progress {
    position: relative;
    padding: 16px 40px 16px 0;
    line-height: 2;
    border-top: 1px solid #dadada;
    border-bottom: 1px solid #dadada;

    @include phone {
      padding: 16px 18px 16px 0;
    }

    &::before {
      content: "";
      position: absolute;
      left: 0;
      width: 1px;
      height: 76px;
      background-color: #dadada;
      z-index: 2;
    }

    & li {
      padding-left: 6px;
    }

    &-count {
      font-weight: 700;
    }

    &-text,
    &-count {
      z-index: 2;
    }
  }

  &__progress-a,
  &__progress-b,
  &__progress-c,
  &__total {
    position: relative;
    display: flex;
    justify-content: space-between;
  }

  &__progress-a::before,
  &__progress-b::before,
  &__progress-c::before {
    content: "";
    position: absolute;
    left: 0;
    height: 24px;
    border-radius: 0px 3px 3px 0px;
    z-index: 1;
  }

  &__progress-a::before {
    width: 75%;
    background-color: #b1e19b;
  }

  &__progress-b::before {
    width: 15%;
    background-color: #ace2f8;
  }

  &__progress-c::before {
    width: 7%;
    background-color: #ace2f8;
  }

  &__total {
    padding-right: 40px;
    font-size: 16px;
    font-weight: 700;
    line-height: 1.6;
    @include phone {
      padding-right: 20px;
    }
  }
}
</style>
