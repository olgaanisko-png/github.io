<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Калькулятор стоимости сотрудника</title>
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      background: #EAF2FB;
      font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
      padding: 2rem;
    }

    .calc-wrap {
      background: #1560A8;
      border-radius: 20px;
      padding: 2.5rem 2rem 2rem;
      width: 100%;
      max-width: 480px;
    }

    .calc-eyebrow {
      font-size: 11px;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      color: rgba(255,255,255,0.5);
      margin-bottom: 6px;
    }

    .calc-title {
      font-size: 22px;
      font-weight: 600;
      color: #fff;
      margin-bottom: 2rem;
      line-height: 1.3;
    }

    .input-label {
      font-size: 12px;
      color: rgba(255,255,255,0.6);
      margin-bottom: 8px;
      letter-spacing: 0.04em;
    }

    .input-wrap {
      position: relative;
      margin-bottom: 2rem;
    }

    .input-wrap input {
      width: 100%;
      background: rgba(255,255,255,0.12);
      border: 1px solid rgba(255,255,255,0.25);
      border-radius: 12px;
      color: #fff;
      font-size: 28px;
      font-weight: 600;
      padding: 14px 56px 14px 18px;
      outline: none;
      transition: border-color 0.2s, background 0.2s;
    }

    .input-wrap input::placeholder { color: rgba(255,255,255,0.25); }

    .input-wrap input:focus {
      border-color: rgba(255,255,255,0.6);
      background: rgba(255,255,255,0.18);
    }

    .input-wrap input::-webkit-outer-spin-button,
    .input-wrap input::-webkit-inner-spin-button { -webkit-appearance: none; }

    .currency {
      position: absolute;
      right: 18px;
      top: 50%;
      transform: translateY(-50%);
      font-size: 18px;
      font-weight: 500;
      color: rgba(255,255,255,0.4);
      pointer-events: none;
    }

    .results {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 12px;
    }

    .card {
      background: #fff;
      border-radius: 14px;
      padding: 1.25rem 1rem;
      display: flex;
      flex-direction: column;
      gap: 6px;
    }

    .card-icon {
      width: 32px;
      height: 32px;
      border-radius: 8px;
      background: #E6F1FB;
      display: flex;
      align-items: center;
      justify-content: center;
      margin-bottom: 4px;
    }

    .card-label {
      font-size: 12px;
      color: #888;
      line-height: 1.3;
    }

    .card-value {
      font-size: 22px;
      font-weight: 600;
      color: #1560A8;
      line-height: 1.1;
    }

    .card-value.empty { color: #ccc; }

    .card-sub {
      font-size: 11px;
      color: #aaa;
    }
  </style>
</head>
<body>

  <div class="calc-wrap">
    <div class="calc-eyebrow">Калькулятор</div>
    <div class="calc-title">Стоимость работы<br>сотрудника</div>

    <div class="input-label">Оклад на руки в месяц</div>
    <div class="input-wrap">
      <input type="number" id="salary" placeholder="0" min="0" step="500" oninput="calc()" />
      <span class="currency">₽</span>
    </div>

    <div class="results">
      <div class="card">
        <div class="card-icon">
