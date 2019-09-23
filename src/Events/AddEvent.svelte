<script>
  import Select from "svelte-select";
  import DatePicker from "svelte-calendar";
  import FaRegClock from "svelte-icons/fa/FaRegClock.svelte";
  import FaRegCalendar from "svelte-icons/fa/FaRegCalendar.svelte";
  import { internationalize } from "timeUtils";
  import { formatDate } from "timeUtils";
  

   let name = "";
   let startDate = "";
   let startTime = "";
   let endDate = "";
   let endTime ="";
   let category = "";
   let location = "";
   let description = ""
   let streetAddress = "";
   let price = "";
   let image = "";
   let favStatus = false;
  
  
  
  
  let items = [
    { value: "art", label: "Arte" },
    { value: "bike", label: "Bici" },
    { value: "movies", label: "Cine" },
    { value: "talks", label: "Conferencias, Conversatorios" },
    { value: "lifestyle", label: "Estilo de Vida" },
    { value: "family", label: "Familiar" },
    { value: "talks", label: "Conferencias, Conversatorios" }
  ];

  internationalize({
    daysOfWeek: [
      "Domingo",
      "Lunes",
      "Martes",
      "Miércoles",
      "Jueves",
      "Viernes",
      "Sábado"
    ],
    monthsOfYear: [
      "Enero",
      "Febrero",
      "Marzo",
      "Abril",
      "Mayo",
      "Junio",
      "Julio",
      "Agosto",
      "Septiembre",
      "Octubre",
      "Noviembre",
      "Diciembre"
    ]
  });
  let dateFormat = "#{l} #{j} de #{F} de #{Y}";
  let dateChosen;
  let formattedSelected;
  let moreDays;

  function addEvent() {
    const newEvent = {
      id: Math.random().toString(),
      name: name,
      description: description,
      startDate: formattedSelected,

    };
    events = [newEvent, ...events]
  }
</script>

<style>
  .form-wrap {
    margin: 20px;
  }
  .themed {
    --multiItemActiveBG: var(--main_focus);
    --placeholderColor: var(--main_black);
    --borderFocusColor: var(--main_black);
    --multiClearHoverFill: var(--main_innactive);
  }
  .themed:focus {
    border-color: var(--main_focus);
    outline: none;
  }
  .inputform {
    border-color: #d8d8d8;
    border-style: solid;
    outline: none;
    border-width: 1px;
    border-radius: 4px;
    line-height: 16px;
    padding: 10px;
    width: 98%;
    font-size: 0.9rem;
  }
  .inputform:focus {
    border-color: var(--main_black);
  }
  label {
    margin-bottom: 1rem;
    width: 100%;
    font-family: var(--main_header);
    }
  textarea {
    font-family: inherit;
  }

  .form-control {
    padding: 0.5rem 0;
    width: 100%;
    margin: 0.25rem 0;
  }

  .date-time-wrapper {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(500px, 1fr));
  }
  .datetime-container {
    display: flex;
    justify-content: center;
  }

  .datepicker-container {
    display: flex;
    align-content: center;
  }

  .time-container {
    display: flex;
    align-content: center;
  }

  .custom-button {
    border-color: #d8d8d8;
    border-style: solid;
    outline: none;
    border-width: 1px;
    border-radius: 4px;
    line-height: 16px;
    padding: 10px;
    font-size: 0.9rem;
  }
  .icon {
    width: 30px;
    height: 30px;
    padding: 0 10px 0 10px;
  } 
  #eventTime {
    font-family: inherit;
    border-color: #d8d8d8;
    border-style: solid;
    outline: none;
    border-width: 1px;
    border-radius: 4px;
    line-height: 16px;
    padding: 10px;
    font-size: 0.9rem;
  }
</style>

<main class="inner">
  <form on:submit|preventDefault="{addEvent}">
    <div class="form-wrap">
    <h2>Detalles del evento</h2>
      <div class="form-control">
        <label for="name">Nombre del Evento</label>
        <input
          class="inputform"
          type="text"
          id="name"
          placeholder="Escribe el nombre del evento"
          required 
          bind:value={name}/>
      </div>

      <div class="form-control">
        <label for="name">Descripción</label>
        <textarea
          class="inputform"
          type="text"
          id="description"
          placeholder="Añade una pequeña descripción del evento"
          required bind:value={description}/>
      </div>
      <div class="form-control themed">
        <label for="name">Categoría del Evento</label>
        <Select
          {items}
          isMulti={true}
          placeholder="Selecciona o escribe las categorías del evento"
          noOptionsMessage="No se encontraron categorías" />
      </div>
      <div class="form-control">
        <label for="date">Fecha y hora del evento</label>
        <div class="date-time-wrapper">
          <div class="date-time-inner">
            <p>Comienza</p>
            <div class="datetime-container">
              <div class="datepicker-container">
                <div class="icon">
                  <FaRegCalendar />
                </div>
                <DatePicker
                  format={dateFormat}
                  bind:formattedSelected
                  bind:dateChosen>
                  <button class="custom-button">
                    {#if dateChosen}
                      Fecha: {formattedSelected}
                    {:else}Escoge una fecha{/if}
                  </button>
                </DatePicker>
              </div>
              <div class="time-container">
                <div class="icon">
                  <FaRegClock />
                </div>
                <select id="eventTime" name="eventTime">

                  <option value="05:00">05:00 AM</option>
                  <option value="05:30">05:30 AM</option>
                  <option value="06:00">06:00 AM</option>
                  <option value="06:30">06:30 AM</option>
                  <option value="07:00">07:00 AM</option>
                  <option value="07:30">07:30 AM</option>
                  <option value="08:00">08:00 AM</option>
                  <option value="08:30">08:30 AM</option>
                  <option value="09:00">09:00 AM</option>
                  <option value="09:30">09:30 AM</option>
                  <option value="10:00">10:00 AM</option>
                  <option value="10:30">10:30 AM</option>
                  <option value="11:00">11:00 AM</option>
                  <option value="11:30">11:30 AM</option>
                  <option value="12:00">12:00 PM</option>
                  <option value="12:30">12:30 PM</option>
                  <option value="13:00">01:00 PM</option>
                  <option value="13:30">01:30 PM</option>
                  <option value="14:00">02:00 PM</option>
                  <option value="14:30">02:30 PM</option>
                  <option value="15:00" selected="selected">03:00 PM</option>
                  <option value="15:30">03:30 PM</option>
                  <option value="16:00">04:00 PM</option>
                  <option value="16:30">04:30 PM</option>
                  <option value="17:00">05:00 PM</option>
                  <option value="17:30">05:30 PM</option>
                  <option value="18:00">06:00 PM</option>
                  <option value="18:30">06:30 PM</option>
                  <option value="19:00">07:00 PM</option>
                  <option value="19:30">07:30 PM</option>
                  <option value="20:00">08:00 PM</option>
                  <option value="20:30">08:30 PM</option>
                  <option value="21:00">09:00 PM</option>
                  <option value="21:30">09:30 PM</option>
                  <option value="22:00">10:00 PM</option>
                  <option value="22:30">10:30 PM</option>
                  <option value="23:00">11:00 PM</option>
                  <option value="23:30">11:30 PM</option>
                </select>
              </div>
            </div>
          </div>
          <div class="date-time-inner">
            <p>Termina</p>
            <div class="datetime-container">
              <div class="datepicker-container">
                <div class="icon">
                  <FaRegCalendar />
                </div>
                <DatePicker
                  format={dateFormat}
                  bind:formattedSelected
                  bind:dateChosen>
                  <button class="custom-button">
                    {#if dateChosen}
                      Fecha: {formattedSelected}
                    {:else}Escoge una fecha{/if}
                  </button>
                </DatePicker>
              </div>
              <div class="time-container">
                <div class="icon">
                  <FaRegClock />
                </div>
                <select id="eventTime" name="eventTime">

                  <option value="05:00">05:00 AM</option>
                  <option value="05:30">05:30 AM</option>
                  <option value="06:00">06:00 AM</option>
                  <option value="06:30">06:30 AM</option>
                  <option value="07:00">07:00 AM</option>
                  <option value="07:30">07:30 AM</option>
                  <option value="08:00">08:00 AM</option>
                  <option value="08:30">08:30 AM</option>
                  <option value="09:00">09:00 AM</option>
                  <option value="09:30">09:30 AM</option>
                  <option value="10:00">10:00 AM</option>
                  <option value="10:30">10:30 AM</option>
                  <option value="11:00">11:00 AM</option>
                  <option value="11:30">11:30 AM</option>
                  <option value="12:00">12:00 PM</option>
                  <option value="12:30">12:30 PM</option>
                  <option value="13:00">01:00 PM</option>
                  <option value="13:30">01:30 PM</option>
                  <option value="14:00">02:00 PM</option>
                  <option value="14:30">02:30 PM</option>
                  <option value="15:00" selected="selected">03:00 PM</option>
                  <option value="15:30">03:30 PM</option>
                  <option value="16:00">04:00 PM</option>
                  <option value="16:30">04:30 PM</option>
                  <option value="17:00">05:00 PM</option>
                  <option value="17:30">05:30 PM</option>
                  <option value="18:00">06:00 PM</option>
                  <option value="18:30">06:30 PM</option>
                  <option value="19:00">07:00 PM</option>
                  <option value="19:30">07:30 PM</option>
                  <option value="20:00">08:00 PM</option>
                  <option value="20:30">08:30 PM</option>
                  <option value="21:00">09:00 PM</option>
                  <option value="21:30">09:30 PM</option>
                  <option value="22:00">10:00 PM</option>
                  <option value="22:30">10:30 PM</option>
                  <option value="23:00">11:00 PM</option>
                  <option value="23:30">11:30 PM</option>
                </select>
              </div>
            </div>
          </div>

        </div>

        <p>¿El evento dura más de un día?</p>
        <input
          class="radio-button"
          type="radio"
          name="moreDays"
          value="singleDay"
          checked />
        No
        <input
          class="radio-button"
          type="radio"
          name="moreDays"
          value="multipleDays" />
        Si
      </div>
      <div class="form-control">
        <label for="location">Nombre del lugar</label>
        <input
          class="inputform"
          type="text"
          id="location"
          placeholder="Escribe el nombre del lugar"
          required 
          bind:value={location}/>
      </div>

       <div class="form-control">
        <label for="streetAddress" >Dirección del lugar</label>
        <input
          class="inputform"
          type="text"
          id="location"
          placeholder="¿Cual es la dirección?"
          required 
          bind:value={streetAddress}/>
      </div>

      <button class="" type="submit">Guardar Evento</button>
    </div>
  </form>
</main>
