<template>
  <v-container
    class="d-flex bg-gradient justify-center align-center fill-height"
    fluid
  >
    <v-card class="form-card">
      <div class="content">
        <v-card-title class="headline font-weight-bold text-center"
          >Sign Up for Free</v-card-title
        >
        <v-card-subtitle class="subtitle text-center">
          Welcome, let's get to know each other!
        </v-card-subtitle>

        <v-form v-model="valid" lazy-validation>
          <label for="fullNameInput" class="input-label">Full Name</label>
          <v-text-field
            id="fullNameInput"
            placeholder="Enter your full name"
            v-model="fullName"
            variant="outline"
            required
            class="input-field mt-2 mb-5"
            :hide-details="true"
          ></v-text-field>
          <label for="fulEmailInput" class="input-label">Email</label>
          <v-text-field
            id="fulEmailInput"
            placeholder="Enter your email"
            v-model="email"
            variant="outline"
            required
            class="input-field mt-2 mb-5"
            :hide-details="true"
          ></v-text-field>
          <label for="fulPhoneInput" class="input-label">Phone number</label>
          <v-text-field
            id="fulPhoneInput"
            placeholder="Enter your phone number"
            v-model="phone"
            required
            variant="outline"
            class="input-field mt-2 mb-8"
            :hide-details="true"
          ></v-text-field>

          <v-btn block class="continue-btn mb-5" @click="submit">
            Continue
          </v-btn>

          <v-btn block class="signin-btn mb-10" @click="signIn">
            I have an account
          </v-btn>
        </v-form>

        <v-card-text class="text-center disclaimer pa-0">
          By signing up, you agree to the
          <a href="#" class="link">Terms of Service</a> and
          <a href="#" class="link">Privacy Policy</a>
        </v-card-text>
      </div>
    </v-card>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      valid: false,
      fullName: "",
      email: "",
      phone: "",
    };
  },
  methods: {
    submit() {
      if (this.valid) {
        // Handle form submission
        alert("Form submitted!");
      } else {
        alert("Please fill in the required fields.");
      }
    },
    signIn() {
      // Handle sign in
      alert("Redirect to sign in");
    },
  },
};
</script>

<style lang="less" scoped>
.bg-gradient {
  background: linear-gradient(to bottom, #1c1c1c, #000000);
}
.fill-height {
  min-height: 100vh;
  background-color: #121212;
}
label {
  color: #f5f5f6;
}

.form-card {
  position: relative;
  border-radius: 12px;
  padding: 1px;
  overflow: hidden;
  background: transparent;
  &::after,
  &::before {
    content: "";
    position: absolute;
    top: 0;
    height: 100%;
  }
  &::before {
    left: 0;
    width: 1px;
    background: linear-gradient(
      0deg,
      rgba(255, 255, 255, 0) 50%,
      rgba(255, 255, 255, 0.7) 100%
    );
    pointer-events: none; /* Щоб цей елемент не блокував взаємодію з контентом */
  }
  &::after {
    right: 0;
    width: calc(100% - 1px);
    background: linear-gradient(
      0deg,
      rgba(255, 255, 255, 0) 68%,
      rgba(224, 224, 224, 0.4) 100%
    );

    pointer-events: none; /* Щоб цей елемент не блокував взаємодію з контентом */
  }
  .content {
    position: relative;
    border-radius: 12px;
    z-index: 1;
    width: 600px;
    padding: 52px 32px;
    background: linear-gradient(to bottom, #1c1c1c, #000000);
  }
}

.headline {
  color: #95969d;
  font-size: 25px;
  margin-bottom: 8px;
  padding: 0;
}

.subtitle {
  color: #b0b0b0;
  margin-bottom: 8px;
  font-size: 17px;
}

.input-field {
  border-radius: 8px;
  color: #ffffff;
  padding: 4px;
  &::v-deep .v-field__input {
    padding: 0 11px;
    min-height: 48px;
    background-color: rgba(39, 39, 41, 0.15);
    border: 1px solid rgba(51, 55, 65, 1);
    border-radius: 8px;

    &:valid {
      border: 2px solid rgba(76, 82, 97, 1);
    }

    &:hover {
      border: 1px solid rgba(128, 128, 128, 1);
    }
    &:focus-within {
      border: 2px solid rgba(204, 204, 204, 1);
    }
  }
}

.continue-btn {
  background-color: #ffffff;
  color: rgba(22, 27, 38, 1);
  border-radius: 8px;
  height: 52px !important;
  text-transform: capitalize;
  font-size: 17px;
  &:hover {
    background-color: rgba(204, 204, 204, 1);
  }
  &:active {
    background-color: rgba(179, 179, 179, 1);
  }
}
&:focus-within {
  .continue-btn {
    background-color: rgba(255, 255, 255, 0.3);
  }
}
.signin-btn {
  color: #ffffff;
  font-weight: 600;
  text-transform: none;
  height: 52px !important;
  border-radius: 8px;
  border: 1px solid rgba(98, 100, 109, 1);
  background: rgba(39, 39, 41, 0.3);
  box-shadow: 0 -2px 2px 0 rgba(52, 64, 84, 0.05),
    0 1px 0 0 rgba(52, 64, 84, 0.02);
  &:hover {
    background-color: rgba(39, 39, 41, 0.7);
  }
  &:active {
    background-color: rgba(39, 39, 41, 1);
  }
}

.disclaimer {
  color: #666666;
  font-size: 12px;
  margin-top: 32px;
}

.link {
  color: #ffffff;
  font-weight: 500;
  text-decoration: underline;
}
</style>
