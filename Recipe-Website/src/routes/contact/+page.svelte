<nav class="navbar">

    <a href="/">Home</a>
    <a href="/recipe">R.O.T.D.</a>
    <a href="/contact">Contact</a>
    <a href="/about">About Us</a>

</nav>

<script>
    import { supabase } from "$lib/db.js";

    import { createForm } from "svelte-forms-lib";
    import * as yup from "yup";

    import { TextInput, TextArea, Button, FormGroup, Form, InlineNotification } from "carbon-components-svelte";
   
    const validationSchema = yup.object().shape({
        name: yup.string().required('Please enter a name'),
        email: yup.string().email().required('Please enter a valid email'),
        message: yup.string().required('Please enter a message')
    });

    let apiResult = {};

    const { form, errors, handleChange, handleSubmit, isSubmitting, handleReset } = createForm({
        initialValues: { name: "", email: "", subject: "", message: "" },
        validationSchema: validationSchema,
        onSubmit: async values => {

            try {
                var result = await supabase.from("contact").insert(values);

                if (result.data != null) {
                    apiResult = true;
                } else {
                    apiResult = false;
                }

            } catch (ex) {
                apiResult = false;
            }

            handleReset();
      }

    });

</script>

<!--  -->
<img class="intro" src="bg.png" alt="Cooking"> 
<div class="Contact">
    <h1>Contact Us</h1>
    <body>
        <div class="Input">
            <Form on:submit={handleSubmit}>
                    <FormGroup>
                        <TextInput labelText="Name" name="name" 
                        on:change={handleChange} bind:value={$form.name}
                        invalid={$errors.name.length > 0} invalidText={$errors.name}/>
                    </FormGroup>
                
                    <FormGroup>
                        <TextInput labelText="Email" name="email" type="email" 
                        on:change={handleChange} bind:value={$form.email}
                        invalid={$errors.email.length > 0} invalidText={$errors.email}/>
                    </FormGroup>
                
                    <FormGroup>
                        <label for="subject">Subject</label>
                        <select
                        id="subject"
                        name="subject"
                        on:change={handleChange}
                        bind:value={$form.subject}>
                        <option value="" disabled selected hidden>Choose a Subject</option>
                        <option value="Problem">Report A Problem</option>
                        <option value="Recipe">Share A Recipe</option>
                        <option value="Contact">Get In Touch</option>
                        </select>
                    </FormGroup>

                    <FormGroup>
                        <TextArea labelText="Message" name="message" type="textarea"
                        on:change={handleChange} bind:value={$form.message}
                        invalid={$errors.message.length > 0} invalidText={$errors.message} width=3px/>
                    </FormGroup>
                <Button type="submit" disabled={$isSubmitting}>Submit</Button>
            </Form>
        </div>
    </body>
</div>

<style>
    .navbar {
        display: flex;
        justify-content: center;
        background-color: rgb(126, 122, 122);
        color: #fff;
        font-family: 'Montserrat', sans-serif;
        font-size: 1.2rem;
        border-bottom: 1px solid #ccc;
        width: 370px; 
        margin: 0 auto; 
    }

    .navbar a {
        color: #fff;
        text-decoration: none;
        padding: 12px;        
        border-right: 1px solid #ccc;
        align-items: center;
    }

    .navbar a:hover {
        background-color: #444; 
    }

    .navbar a:last-child {
        border-right: none;
    }

    .intro {
        background-image: url("bg.png");
        background-size: cover;
        width: min(1268.8px, 105vw);
        height: 646.08px;
    }
    
    .Contact {
        position:absolute;
        top:15%;
        left:3%;
        border-radius: 40px;
        height: 400px;
        width: max(390px, 33vw);
        background-color: powderblue;
    }

    h1 {
        display: flex;
        text-align: left;
        padding-left: 7%;
        margin: 0;
        padding-top: 25px;
    }

    .Input{
        border-radius:10px;
        border-color:transparent;
        width: max(375px, 31.7vw);
    }

</style>