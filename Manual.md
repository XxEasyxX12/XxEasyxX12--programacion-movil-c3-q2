
# Componentes Individuales

Este proyecto incluye una variedad de componentes de Ionic React para construir una interfaz de usuario funcional e interactiva. A continuación, se detallan los componentes usados en el proyecto.

## Componentes

### Selección Múltiple
El componente `ion-select` permite a los usuarios seleccionar múltiples opciones de una lista.
```jsx
<IonList>
  <IonItem>
    <IonSelect aria-label="Fruit" placeholder="Select all fruits that apply" multiple={true}>
      <IonSelectOption value="apples">Apples</IonSelectOption>
      <IonSelectOption value="oranges">Oranges</IonSelectOption>
      <IonSelectOption value="bananas">Bananas</IonSelectOption>
    </IonSelect>
  </IonItem>
</IonList>
```

### Inputs
El componente `ion-input` permite a los usuarios ingresar texto o números.
```jsx
<IonList>
  <IonItem>
    <IonInput label="Text input" placeholder="Enter text"></IonInput>
  </IonItem>
  <IonItem>
    <IonInput label="Number input" type="number" placeholder="000"></IonInput>
  </IonItem>
  <IonItem>
    <IonInput label="Password input" type="password" value="password"></IonInput>
  </IonItem>
  <IonItem>
    <IonInput label="Email input" type="email" placeholder="email@domain.com"></IonInput>
  </IonItem>
  <IonItem>
    <IonInput label="Telephone input" type="tel" placeholder="888-888-8888"></IonInput>
  </IonItem>
</IonList>
```

### Tarjetas De Medios
El componente `ion-card` permite a los usuarios interactuar con tarjetas de medios.
```jsx
<IonCard>
  <img alt="Silhouette of mountains" src="https://ionicframework.com/docs/img/demos/card-media.png" />
  <IonCardHeader>
    <IonCardTitle>Card Title</IonCardTitle>
    <IonCardSubtitle>Card Subtitle</IonCardSubtitle>
  </IonCardHeader>
  <IonCardContent>Here's a small text description for the card content. Nothing more, nothing less.</IonCardContent>
</IonCard>
```

### Ventana Emergentes En Línea
El componente `ion-modal` permite a los usuarios interactuar con ventanas emergentes en línea.
```jsx
<IonButton id="click-trigger">Left-Click Me</IonButton>
<IonPopover trigger="click-trigger" triggerAction="click">
  <IonContent class="ion-padding">Hello World!</IonContent>
</IonPopover>
```

### Barra De Búsqueda
El componente `ion-searchbar` permite a los usuarios buscar contenido en una aplicación.
```jsx
<IonSearchbar placeholder="Custom Placeholder"></IonSearchbar>
```

### Botón
El componente `ion-button` permite a los usuarios interactuar con botones.
```jsx
<IonButton className="seleccionar">
  Click Aquí
</IonButton>
```

### Radio
El componente `ion-radio` permite a los usuarios interactuar con botones de radio.
```jsx
<IonRadioGroup value="strawberries">
  <IonRadio value="grapes">Grapes</IonRadio>
  <br />
  <IonRadio value="strawberries">Strawberries</IonRadio>
  <br />
  <IonRadio value="pineapple">Pineapple</IonRadio>
  <br />
  <IonRadio value="cherries">Cherries</IonRadio>
</IonRadioGroup>
```

### Tematización 

El componente `ion-toggle` permite a los usuarios interactuar con botones de radio.
```jsx
<IonSegmentButton value="default">
  <IonLabel>Hombre</IonLabel>
</IonSegmentButton>
<IonSegmentButton value="segment">
  <IonLabel>Mujer</IonLabel>
</IonSegmentButton>
```

### Alternar Lista Toggle

El componente `ion-toggle` permite a los usuarios interactuar con botones de radio.
```jsx
<IonList>
  <IonItem>
    <IonToggle>Receive Push Notifications</IonToggle>
  </IonItem>
  <IonItem>
    <IonToggle>Receive Emails</IonToggle>
  </IonItem>
  <IonItem>
    <IonToggle>Receive Text Messages</IonToggle>
  </IonItem>
</IonList>
```

### Footer 
El componente `ion-footer` permite a los usuarios interactuar con botones.
```jsx
<IonFooter>
  <IonToolbar className="footer">
    <IonTitle>Encuéntranos en:</IonTitle>
    <div className="social-icons">
      <a href="https://www.facebook.com" target="_blank" rel="noopener noreferrer">
        <IonIcon icon={logoFacebook} className="icon" />
      </a>
      <a href="https://www.twitter.com" target="_blank" rel="noopener noreferrer">
        <IonIcon icon={logoTwitter} className="icon" />
      </a>
      <a href="https://www.instagram.com" target="_blank" rel="noopener noreferrer">
        <IonIcon icon={logoInstagram} className="icon" />
      </a>
    </div>
  </IonToolbar>
</IonFooter>

## Componentes Crud

### Formulario

<div className="formulario">
    <div className="title caja">
        <h1>Completa El Formulario</h1>
    </div>

    <IonItem className='inputs-formu'>
        <IonLabel position="floating">Nombre</IonLabel>
        <IonInput value={name} onIonChange={(e) => setName(e.target.value)} />
    </IonItem>
    <IonItem className='inputs-formu'>
        <IonLabel position="floating">Apellidos</IonLabel>
        <IonInput value={surname} onIonChange={(e) => setSurname(e.target.value)} />
    </IonItem>
    <IonItem className='inputs-formu'>
        <IonLabel position="floating">Correo</IonLabel>
        <IonInput value={email} onIonChange={(e) => setEmail(e.target.value)} />
    </IonItem>
    <IonItem className='inputs-formu'>
        <IonLabel position="floating">Contraseña</IonLabel>
        <IonInput type="password" value={password} onIonChange={(e) => setPassword(e.target.value)} />
    </IonItem>
    <IonButton className='crear' onClick={handleSubmit}>
        {editIndex !== null ? 'Actualizar' : 'Crear'}
    </IonButton>

    <IonList className='lista-formu'>
        {users.map((user, index) => (
            <IonItem key={index}>
                <IonLabel>
                    {user.name} {user.surname} - {user.email}
                </IonLabel>
                <IonButton onClick={() => handleEdit(index)}>Editar</IonButton>
                <IonButton color="danger" onClick={() => handleDelete(index)}>Eliminar</IonButton>
            </IonItem>
        ))}
    </IonList>
</div>

### Botones Crear, Actualizar Y Eliminar

<div className="botones">
    <IonButton color="primary">Crear</IonButton>
    <IonButton color="secondary">Actualizar</IonButton>
    <IonButton color="danger">Eliminar</IonButton>
</div>

