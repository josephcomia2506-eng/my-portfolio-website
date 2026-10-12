<script setup>
	import { Notyf } from 'notyf';
    import 'notyf/notyf.min.css';

    const notyf = new Notyf();

    const WEB3FORMS_ACCESS_KEY = "572c2504-2257-4e04-83cd-000c8c653b1c";

    const subject = "New message from Portfolio Contact Form";

    const name = ref("");
    const email = ref("");
    const message = ref("");

    const isLoading = ref(false);

    const submitForm = async () => {

        isLoading.value = true;

        try {
            const response = await fetch("https://api.web3forms.com/submit", {
                method: "POST",
                headers: {
                    "Content-Type": "application/json",
                    Accept: "application/json"
                },
                body: JSON.stringify({
                    access_key: WEB3FORMS_ACCESS_KEY,
                    subject: subject,
                    email: email.value,
                    name: name.value,
                    message: message.value
                })
            })

            const result = await response.json();

            if(result.success) {
                console.log(result);
                isLoading.value = false;
                notyf.success("Message Sent!")
            }
        } catch(e) {
            console.log(e);
            isLoading.value = false;
            notyf.error("Failed to send message. Please try again.")
        } finally {
            resetRecaptcha();
        }
    }
</script>

<template>
	<!-- ================= CONTACT ================= -->
	<section id="contact" class="py-5">
	    <div class="container">
	        <div class="text-center mb-5">
	            <h2 class="section-title">
	                Contact Me
	            </h2>

	            <p class="section-description">
	                Feel free to reach out for collaboration or opportunities.
	            </p>
	        </div>

	        <div class="row">
	            <div class="col-lg-6 mb-4">
	                <iframe
	                    src="https://maps.google.com/maps?q=Sto.%20Tomas%20Batangas&t=&z=13&ie=UTF8&iwloc=&output=embed"
	                    width="100%"
	                    height="400"
	                    style="border:0;"
	                    allowfullscreen=""
	                    loading="lazy">
	                </iframe>
	            </div>

	            <div class="col-lg-6">
	                <form @submit.prevent="submitForm">
	                    <div class="mb-3">

	                        <input
	                            type="text"
	                            class="form-control"
	                            placeholder="Full Name" v-model="name">
	                    </div>

	                    <div class="mb-3">
	                        <input
	                            type="email"
	                            class="form-control"
	                            placeholder="Email Address" v-model="email">
	                    </div>

	                    <div class="mb-3">
	                        <textarea
	                            class="form-control"
	                            rows="7"
	                            placeholder="Message" v-model="message"></textarea>
	                    </div>

	                    <button class="btn btn-primary w-100":disabled="isLoading">{{ isLoading ? "Sending..." : "Send Message" }}
	                    </button>
	                </form>
	            </div>
	        </div>
	    </div>
	</section>
</template>