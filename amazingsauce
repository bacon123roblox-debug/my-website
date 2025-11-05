<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Interactive Periodic Table - Resource Quantities</title>
  <style>
    /* --- Reset & Base Styles --- */
    * { margin: 0; padding: 0; box-sizing: border-box; font-family: Arial, sans-serif; }
    body { background: #f4f4f9; color: #333; }
    h1 { text-align: center; margin: 20px 0; color: #222; }
    
    /* --- Table Grid --- */
    .periodic-table {
      display: grid;
      grid-template-columns: repeat(18, 50px);
      gap: 4px;
      justify-content: center;
      margin: 20px;
    }
    
    .element {
      background: linear-gradient(135deg, #6fa8dc, #3d85c6);
      color: white;
      border-radius: 6px;
      padding: 5px;
      text-align: center;
      cursor: pointer;
      transition: transform 0.2s, background 0.3s;
    }
    
    .element:hover {
      transform: scale(1.1);
      background: linear-gradient(135deg, #3d85c6, #6fa8dc);
    }
    
    .element span {
      display: block;
      font-size: 0.7em;
      margin-top: 2px;
    }
    
    /* --- Popup Styles --- */
    .popup {
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      width: 50%;
      max-width: 600px;
      max-height: 80%;
      background: white;
      border-radius: 12px;
      box-shadow: 0 10px 30px rgba(0,0,0,0.2);
      padding: 20px;
      overflow-y: auto;
      z-index: 100;
      display: none;
      animation: fadeIn 0.3s ease-in-out;
    }
    
    @keyframes fadeIn {
      from { opacity: 0; transform: translate(-50%, -52%); }
      to { opacity: 1; transform: translate(-50%, -50%); }
    }

    .popup h2 { margin-bottom: 10px; color: #3d85c6; }
    .popup p { margin-bottom: 12px; line-height: 1.4; }
    .popup .close-btn {
      position: absolute;
      top: 10px;
      right: 15px;
      cursor: pointer;
      font-size: 1.3em;
      color: #888;
    }
    .popup .close-btn:hover { color: #333; }
    
    /* --- Footer --- */
    footer { text-align: center; margin: 20px; font-size: 0.9em; color: #555; }
  </style>
</head>
<body>

  <h1>Periodic Table of Resource Quantities</h1>

  <div class="periodic-table">
    <!-- Example elements -->
    <div class="element" data-name="Hydrogen" data-info="Hydrogen is the most abundant element in the universe. On Earth, it is mostly found in water. It is used in fuel cells, ammonia production, and refining processes. We are not running out of hydrogen; the main concern is extracting it sustainably. Its environmental impact is low when used cleanly, but production via fossil fuels emits CO2.">
      H <span>1</span>
    </div>
    <div class="element" data-name="Helium" data-info="Helium is rare on Earth but abundant in the universe. It is used in balloons, medical imaging (MRI), and scientific experiments. Supplies are limited because it slowly escapes the atmosphere. Running out is a real risk; it is extracted from natural gas. Environmentally, helium extraction has minimal impact but can waste associated gases.">
      He <span>2</span>
    </div>
    <div class="element" data-name="Lithium" data-info="Lithium is crucial for batteries, especially for electric vehicles and electronics. Major reserves are in South America and Australia. Supplies are growing, but demand is skyrocketing. Over-extraction can damage ecosystems, use lots of water, and cause soil degradation. Sustainable mining is a challenge.">
      Li <span>3</span>
    </div>
    <!-- Add more elements similarly -->
  </div>

  <!-- Popup -->
  <div class="popup" id="popup">
    <span class="close-btn" id="closeBtn">&times;</span>
    <h2 id="popupTitle"></h2>
    <p id="popupContent"></p>
  </div>

  <footer>Interactive Periodic Table by Liam | Static HTML/CSS/JS Project</footer>

  <script>
    const elements = document.querySelectorAll('.element');
    const popup = document.getElementById('popup');
    const popupTitle = document.getElementById('popupTitle');
    const popupContent = document.getElementById('popupContent');
    const closeBtn = document.getElementById('closeBtn');

    elements.forEach(el => {
      el.addEventListener('click', () => {
        popup.style.display = 'block';
        popupTitle.textContent = el.dataset.name;
        // Split the info into 5 paragraphs for better readability
        const info = el.dataset.info.split('. ').map((p, i, arr) => {
          if(i < 4) return p + '.';
          return arr.slice(i).join('. ');
        });
        popupContent.innerHTML = info.map(p => `<p>${p}</p>`).join('');
      });
    });

    closeBtn.addEventListener('click', () => {
      popup.style.display = 'none';
    });

    // Close popup if clicking outside
    window.addEventListener('click', (e) => {
      if(e.target === popup) popup.style.display = 'none';
    });
  </script>

</body>
</html>
