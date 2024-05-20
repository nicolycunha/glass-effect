<template>
  <div class="card">
    <div class="header">
      <h1>Acesse sua conta</h1>
      <p>Que bom te ver novamente!</p>
    </div>
    <div class="login-methods">
      <Button v-for="button in buttons" :key="button.id" :button="button" />
    </div>
    <div class="divider">ou</div>
    <form action="" class="form">
      <Field v-for="field in fields" :key="field.type" :field="field" />
      <ButtonLogin />
    </form>
    <div class="footer">
      <p class="footer-text emphasis">Esqueceu a senha?</p>
      <p class="footer-text first-access">
        Primeiro acesso?
        <span class="emphasis">Crie sua conta</span>
      </p>
    </div>
  </div>
</template>

<script lang="ts">
import Button from "./Button.vue";
import ButtonLogin from "./ButtonLogin.vue";
import Field from "./Field.vue";
import { ref } from "vue";
import { v4 as uuidv4 } from "uuid";
import { IButton } from "../interfaces/Button";
import { IForm } from "../interfaces/Form";
import { IField } from "../interfaces/Field";

export default {
  name: "Card",
  components: {
    Button,
    ButtonLogin,
    Field,
  },
  setup(_) {
    const buttons = ref<IButton[]>([
      {
        id: uuidv4(),
        text: "Login com Google",
        image: "/src/assets/images/google.png",
      },
      {
        id: uuidv4(),
        text: "Login com Apple",
        image: "/src/assets/images/apple.png",
      },
    ]);

    const form = ref<IForm>({
      email: "",
      pass: "",
    });

    const fields = ref<IField[]>([
      {
        text: "E-mail",
        value: form.value.email,
        type: "email",
        placeholder: "Digite seu e-mail",
      },
      {
        text: "Senha",
        value: form.value.pass,
        type: "password",
        placeholder: "Digite sua senha",
      },
    ]);

    return {
      buttons,
      form,
      fields,
    };
  },
};
</script>

<style scoped>
.card {
  margin: 48px auto;
  max-width: 500px;
  min-width: 300px;
  min-height: 70vh;
  padding: 35px;
  gap: 16px;
  border-radius: 16px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  background: rgba(255, 255, 255, 0.25);
  border: 1px solid rgba(255, 255, 255, 0.5);
  box-shadow: 0 0 10px 1px rgba(0, 0, 0, 0.25);
  backdrop-filter: blur(5px);
}

.header h1,
.header p {
  margin: 0;
}

.login-methods {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 16px;
}

.divider {
  display: flex;
  align-items: center;
}

.divider::after,
.divider::before {
  background-color: #000000;
  content: "";
  height: 1px;
  width: 100%;
}

.divider::after {
  margin: 0 0 0 12px;
}

.divider::before {
  margin: 0 12px 0 0;
}

.form {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 16px;
}

.footer-text,
.login-methods {
  font-family: "IBM Plex Sans", Inter, sans-serif;
  font-weight: 500;
}

.footer-text {
  margin: 8px 0;
}

.emphasis {
  color: #ff1b6b;
}
</style>