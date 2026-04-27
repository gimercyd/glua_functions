<div align="center">
  <h1>Удобные glua функции</h1>
</div>

<div align="center">
  <h2>DarkRP</h2>
  <h3>Функция для поиска категории</h3>
</div>

<div>
  <pre><code>
    function getPlayerCategory(ply)
      if not IsValid(ply) then return nil end
      local job = RPExtraTeams[ply:Team()]
      return job and job.category or nil
    end
  </code></pre>
  <p1><b>Важное примечание!</b> Не советую использовать <code>team.GetInfo(ply:Team())</code>. Мой метод null safety.</p1>
</div>
