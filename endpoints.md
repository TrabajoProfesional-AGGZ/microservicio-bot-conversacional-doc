---
layout: default
title: Endpoints
nav_order: 2
---

# 🔌 Endpoints

En esta sección se listan los endpoints disponibles en el microservicio del bot conversacional de Telegram (BotIn).

Esta página sirve como referencia estática para garantizar el acceso a los contratos de la API de forma rápida y clara, abarcando las rutas de notificación y diagnóstico de salud.

## Listado de Endpoints

A continuación, haz clic en cada bloque para desplegar los detalles de la petición, parámetros y respuestas.

<details>
  <summary style="font-size: 1.1em; cursor: pointer; padding: 10px; background-color: #f8f9fa; border-radius: 4px; border-left: 4px solid #28a745; margin-bottom: 5px;">
    <strong style="color: #28a745;">POST</strong> <code>/api/v1/bot/notificar</code> - Notificar
  </summary>
  <div style="padding: 15px; border: 1px solid #f8f9fa; border-top: none; margin-bottom: 20px;">
    
    <p><strong>ID de la Operación:</strong> <code>notificar_api_v1_bot_notificar_post</code></p>
    
    <p>Recibe una alerta o noticia proveniente del microservicio core (<code>ms-club</code>) y la reenvía masivamente a todos los socios registrados a través de Telegram.</p>

    <h3>Parámetros</h3>
    <ul>
      <li><strong>Header:</strong> <code>x-internal-token</code> (String, Opcional) - Token interno de autenticación entre microservicios.</li>
    </ul>

    <h3>Cuerpo de la Petición (Request Body)</h3>
    <p><strong>Content-Type:</strong> <code>application/json</code> (Requerido)</p>

    <div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{</span><span class="w">
  </span><span class="nl">"mensaje"</span><span class="p">:</span><span class="w"> </span><span class="s2">"string"</span><span class="w"> </span><span class="err">// Obligatorio (Min: 1, Max: 4096 caracteres)</span><span class="w">
</span><span class="p">}</span>
</code></pre></div></div>

    <h3>Respuestas</h3>

    <p><strong>Código:</strong> <code>200 OK</code></p>
    <ul>
      <li><strong>Descripción:</strong> Successful Response</li>
    </ul>
    <div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{}</span>
</code></pre></div></div>

    <p><strong>Código:</strong> <code>422 Unprocessable Entity</code></p>
    <ul>
      <li><strong>Descripción:</strong> Validation Error</li>
    </ul>

  </div>
</details>

<details>
  <summary style="font-size: 1.1em; cursor: pointer; padding: 10px; background-color: #f8f9fa; border-radius: 4px; border-left: 4px solid #007bff; margin-bottom: 5px;">
    <strong style="color: #007bff;">GET</strong> <code>/health</code> - Health Check
  </summary>
  <div style="padding: 15px; border: 1px solid #f8f9fa; border-top: none; margin-bottom: 20px;">
    
    <p><strong>ID de la Operación:</strong> <code>health_check_health_get</code></p>
    
    <p>Endpoint estándar para verificar que el microservicio y su servidor HTTP están funcionando correctamente.</p>

    <h3>Respuestas</h3>

    <p><strong>Código:</strong> <code>200 OK</code></p>
    <ul>
      <li><strong>Descripción:</strong> Successful Response</li>
    </ul>
    <div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{}</span>
</code></pre></div></div>

  </div>
</details>

<details>
  <summary style="font-size: 1.1em; cursor: pointer; padding: 10px; background-color: #f8f9fa; border-radius: 4px; border-left: 4px solid #007bff; margin-bottom: 5px;">
    <strong style="color: #007bff;">GET</strong> <code>/health/bot</code> - Health Bot
  </summary>
  <div style="padding: 15px; border: 1px solid #f8f9fa; border-top: none; margin-bottom: 20px;">
    
    <p><strong>ID de la Operación:</strong> <code>health_bot_health_bot_get</code></p>
    
    <p>Diagnóstico avanzado que evalúa el estado real y la conexión activa del bot con la API de Telegram (más allá de comprobar si el proceso web está activo).</p>

    <h3>Respuestas</h3>

    <p><strong>Código:</strong> <code>200 OK</code></p>
    <ul>
      <li><strong>Descripción:</strong> Successful Response</li>
    </ul>
    <div class="language-json highlighter-rouge"><div class="highlight"><pre class="highlight"><code><span class="p">{}</span>
</code></pre></div></div>

  </div>
</details>
