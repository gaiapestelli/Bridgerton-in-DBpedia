<!DOCTYPE html>
<html lang="it">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>BRIDGERTON in DBpedia</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      max-width: 900px;
      margin: auto;
      padding: 20px;
      line-height: 1.6;
    }
    header {
      text-align: center;
      margin-bottom: 40px;
    }
    nav {
      background: #007bff;
      padding: 10px;
      margin-bottom: 30px;
      border-radius: 5px;
      text-align: center;
    }
    nav a {
      color: white;
      margin: 0 15px;
      text-decoration: none;
      font-weight: bold;
      cursor: pointer;
    }
    nav a:hover {
      text-decoration: underline;
    }
    section {
      display: none; /* nascondi tutte le sezioni */
      margin-bottom: 40px;
    }
    section.active {
      display: block; /* mostra solo la sezione attiva */
    }
  </style>
</head>
<body>

<header>
  <h1>Bridgerton in DBpedia</h1>
</header>

<nav>
  <a onclick="showSection('homepage')">Home</a>
  <a onclick="showSection('selected-topic')">Selected Topic Description</a>
  <a onclick="showSection('gap-methodology')">Gap, General Methodology and Tools</a>
  <a onclick="showSection('methodological-steps')">Methodological Steps</a>
  <a onclick="showSection('challenges-llms')">Challenges and LLMs Differences</a>
</nav>

<!-- Sezione homepage visibile all'inizio -->
<section id="homepage" class="active">
  <h2>Abstract</h2>
  <p>
    In this project, we explored and enriched a knowledge graph (KG) about the TV series Bridgerton by combining SPARQL querying techniques with the assistance of large language models (LLMs), specifically ChatGPT (OpenAI) and Gemini (Google). Our goal was to model and assess whether certain concepts (e.g., general information and knowledge, themes, soundtrack) are represented in the graph, and where necessary, propose new triples.
  </p>

  <h2>Partecipanti</h2>
  <ul>
    <li>Alessia Gavelli</li>
    <li>Elisa Mainardi</li>
    <li>Gaia Pestelli</li>
  </ul>
</section>

<section id="selected-topic">
  <h2>Selected Topic Description</h2>
  <p>For our project, we have chosen to focus on the television series Bridgerton, a production that has gained widespread popularity and cultural relevance in recent years.This decision was made collectively, as the series is well-known, widely discussed, and familiar to all members of the group. Bridgerton includes multiple interconnected storylines and social dynamics, making it ideal for building a semantic graph (e.g. DBpedia) where entities and links reflect both explicit and inferred connections. This allows us to apply advanced querying techniques (e.g. Yasgui) to explore patterns, relationships, and hierarchies within the fictional world.

Bridgerton is a historical romance television series created by Chris Van Dusen and produced by Shondaland, based on the bestselling novels by Julia Quinn. The show is set in Regency-era London (early 19th century), a period characterized by rigid social structures, elaborate courtship rituals, and intense pressure to marry advantageously. As of 2025, Bridgerton has released three seasons; additionally, the series has been renewed for Seasons 5 and 6, ensuring the continuation of the Bridgerton family's stories

The narrative primarily follows an affluent family whose members are each introduced to the social season, where finding a suitable marriage partner is both a personal and familial priority. Each season centers on the romantic and emotional development of a different family member, exploring how individual desires often clash with societal expectations. The stories are marked by themes of longing, personal growth, and the delicate balance between public image and private truth. A key narrative device is the presence of an anonymous gossip columnist whose scandalous reports influence public perception and add intrigue to the unfolding events. A companion series to Bridgerton expands the universe by focusing on the early life of a prominent royal figure featured in the main show. “Queen Charlotte: A Bridgerton story” is set in the same alternate version of Regency society, this prequel explores themes such as power, societal change, personal sacrifice, and the pressures of leadership.
Thematically, Bridgerton explores the tension between love and societal obligation, gender roles, and the importance of reputation within the aristocracy. It also addresses female agency, particularly through its female characters who seek autonomy in a patriarchal world. While not historically accurate, the show embraces a diverse and inclusive casting, presenting a reimagined Regency society in which race does not impede social mobility—thus blending historical drama with modern values.
Visually, Bridgerton is known for its opulent production design, featuring grand estates, extravagant costumes, and stylized reinterpretations of period customs. Despite its historical setting, the series often incorporates contemporary music (in classical arrangements) and modern storytelling techniques, creating a fresh, hybrid aesthetic.
.</p>
</section>

<section id="gap-methodology">
  <h2>Gap, General Methodology and Tools</h2>
  <p>Descrizione delle lacune individuate, metodologia generale adottata e strumenti utilizzati.</p>
</section>

<section id="methodological-steps">
  <h2>Methodological Steps</h2>
  <p>Passaggi metodologici seguiti nel corso del progetto.</p>
</section>

<section id="challenges-llms">
  <h2>Challenges and LLMs Differences</h2>
  <p>Discussione sulle sfide incontrate e differenze tra i modelli di linguaggio.</p>
</section>

<script>
  function showSection(id) {
    // Nascondi tutte le sezioni
    document.querySelectorAll('section').forEach(sec => {
      sec.classList.remove('active');
    });
    // Mostra solo la sezione selezionata
    const section = document.getElementById(id);
    if (section) {
      section.classList.add('active');
    }
  }
</script>

</body>
</html>

