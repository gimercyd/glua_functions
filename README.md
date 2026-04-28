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

<div align="center">
  <h2>Прочее</h2>
  <h3>Custom timer</h3>
</div>

<div>
  <pre>
function createTimer(delay, callback)
    local start = CurTime()
    return function()
        if CurTime() >= start + delay then
            callback()
            return true
        end
        return false
    end
end
  </pre>
  <p1><b>Памятка</b> Эта функция недостаточно раскрывает возможности <code>CurTime()</code>, вы можете взять эту функцию за основу и улучшить/обезопасить. Не советую использовать <code>timer.Create</code>, так как при лагах сервера могут возникнуть сбои, также сильно нагружают сам сервер при большом количестве. Также <code>CurTime()</code> отлично работает с хуком <code>Think</code>, который обрабатывает каждый тик сервера.</p1>
</div>
