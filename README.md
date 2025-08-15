<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Anuj Gupta — Indian Food Dishes</title>
  <style>
    body { 
      font-family: 'Segoe UI', sans-serif; 
      background: #0d0d0d; 
      color: #f5f5f5; 
      margin: 0; 
      padding: 0; 
    }
    header { 
      background: linear-gradient(90deg, #1a1a1a, #333); 
      padding: 1.5rem; 
      text-align: center; 
      border-bottom: 2px solid #c8a951;
    }
    header h1 { 
      margin: 0; 
      font-size: 2.5rem; 
      color: #c8a951; 
    }
    header p { 
      margin: 0; 
      color: #ddd; 
      font-style: italic;
    }
    .filters { 
      text-align: center; 
      margin: 1.5rem 0; 
    }
    .filters input, .filters select { 
      padding: 0.7rem; 
      font-size: 1rem; 
      border-radius: 8px; 
      margin: 0.5rem; 
      border: 1px solid #c8a951; 
      background: #1a1a1a; 
      color: #fff; 
      outline: none; 
    }
    ul { 
      list-style: none; 
      padding: 0; 
      display: flex; 
      flex-wrap: wrap; 
      justify-content: center; 
    }
    li { 
      background: #1a1a1a; 
      margin: 0.5rem; 
      padding: 1rem 1.5rem; 
      border-radius: 10px; 
      min-width: 150px; 
      text-align: center; 
      transition: transform 0.3s, background 0.3s;
      border: 1px solid #c8a951;
    }
    li:hover { 
      background: #2a2a2a; 
      transform: scale(1.05); 
    }
    footer { 
      background: linear-gradient(90deg, #1a1a1a, #333); 
      text-align: center; 
      padding: 1rem; 
      margin-top: 2rem; 
      border-top: 2px solid #c8a951;
    }
    a { 
      color: #c8a951; 
      text-decoration: none; 
    }
    a:hover { 
      text-decoration: underline; 
    }
  </style>
</head>
<body>
  <header>
    <h1>Anuj Gupta</h1>
    <p>@anujguptax_ — Indian Food Lover</p>
  </header>

  <div class="filters">
    <label for="searchBar">🔍 Search Dish: </label>
    <input type="text" id="searchBar" placeholder="Type a dish name...">

  <label for="regionFilter">📍 Filter by Region: </label>
    <select id="regionFilter">
      <option value="all">All</option>
      <option value="north">North India</option>
      <option value="south">South India</option>
      <option value="east">East India</option>
      <option value="west">West India</option>
    </select>
  </div>

  <ul id="dishList"></ul>

  <footer>
    <p>📧 Contact: <a href="mailto:anujguptaa999@gmail.com">anujguptaa999@gmail.com</a></p>
    <p>📷 Instagram: <a href="https://instagram.com/anujguptax_" target="_blank">@anujguptax_</a></p>
  </footer>

  <script>
    const dishes = [
      // North India
      { name: 'Butter Chicken', region: 'north' },
      { name: 'Rogan Josh', region: 'north' },
      { name: 'Rajma Chawal', region: 'north' },
      { name: 'Chole Bhature', region: 'north' },
      { name: 'Paneer Tikka', region: 'north' },
      { name: 'Aloo Paratha', region: 'north' },
      { name: 'Kadhi Pakora', region: 'north' },

       // South India
      { name: 'Masala Dosa', region: 'south' },
      { name: 'Idli Sambar', region: 'south' },
      { name: 'Hyderabadi Biryani', region: 'south' },
      { name: 'Appam with Stew', region: 'south' },
      { name: 'Chettinad Chicken', region: 'south' },
      { name: 'Pesarattu', region: 'south' },
      { name: 'Upma', region: 'south' },

      // East India
      { name: 'Prawn Malai Curry', region: 'east' },
      { name: 'Macher Jhol', region: 'east' },
      { name: 'Litti Chokha', region: 'east' },
      { name: 'Chhena Poda', region: 'east' },
      { name: 'Sandesh', region: 'east' },
      { name: 'Shorshe Ilish', region: 'east' },
      { name: 'Aloo Posto', region: 'east' },

      // West India
      { name: 'Dhokla', region: 'west' },
      { name: 'Pav Bhaji', region: 'west' },
      { name: 'Goan Fish Curry', region: 'west' },
      { name: 'Misal Pav', region: 'west' },
      { name: 'Shrikhand', region: 'west' },
      { name: 'Laal Maas', region: 'west' },
      { name: 'Khandvi', region: 'west' }
    ];

    const dishList = document.getElementById('dishList');
    const regionFilter = document.getElementById('regionFilter');
    const searchBar = document.getElementById('searchBar');

    function displayDishes(region, search) {
      dishList.innerHTML = '';
      dishes
        .filter(d => 
          (region === 'all' || d.region === region) &&
          d.name.toLowerCase().includes(search.toLowerCase())
        )
        .forEach(d => {
          const li = document.createElement('li');
          li.textContent = d.name;
          dishList.appendChild(li);
        });
    }

    regionFilter.addEventListener('change', () => {
      displayDishes(regionFilter.value, searchBar.value);
    });

    searchBar.addEventListener('input', () => {
      displayDishes(regionFilter.value, searchBar.value);
    });

    displayDishes('all', '');
  </script>
</body>
</html>
