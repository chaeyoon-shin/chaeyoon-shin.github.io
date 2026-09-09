---
layout: page
title: etc
permalink: /etc/
nav: true
nav_order: 5
---

<script src="https://cdnjs.cloudflare.com/ajax/libs/d3/7.9.0/d3.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/topojson/3.0.2/topojson.min.js"></script>

{% raw %}
<script>const FLAGS={"BE":"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFAAAABFBAMAAAAvJHy2AAAAD1BMVEUAAADvM0D92iXzazZVSgz2L4TiAAAAK0lEQVRIx+3KMREAIAwEsLdQC+AE/6JYX0MvmZO0d8qdFlEURVEURVFcFj+GqMTD+NqXTQAAAABJRU5ErkJggg==","CA":"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFAAAAAoCAMAAABevo0zAAAAQlBMVEX/AAD/R0f/Y2P/29v/6Oj/Cgr/VFT/////Gxv/cnL/h4f/lZX/7+//srL/oKD/XFz/zs7/ycn/NTX/eXn/+Pj/u7s/V1YHAAABDUlEQVRIx+WWy3LDIAxFL0/xsgHb+f9f7aLO0KR2xgEt0qlWwNWcAWkkBBwYXTRctT8JVIoZmDMvUAGKFZiBzAXUmkgBgPpeDwOT8ckCQE4eiePJrgmOJYa2CZYFGJoQWIBTE27DwBqIdBMSUai9QB8LkUX8kRVHFGGJSvQdQAmYBcBM4n4uaAawGEB2AG/33dyA8TGYb8bQnDuYrqTIcwf5CUDlXnk49f4Np1cxnHqeXE7v6EpfpejlWF50b+lt9ki120Ath99iGOs2z6nZ0zHQvvyj5If74VOq3Siwwgk/121dtzp74VAGgXr/52Lc/0DNNIqEwDzbrCsz0HtmoJTMQGuZgUL8uxn7MvAL2t0iyxNQ808AAAAASUVORK5CYII=","CH":"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFAAAABQAgMAAADzfxo+AAAADFBMVEX/AAD/////gID/wMCov4oYAAAANklEQVQ4y2NgGAWUgqmhoWGjgrQTZFoFBFdDQ8NBdANUkDEUCTiMCmIXxBp0owmMXoKjgFQAAH/3gHGvQgbmAAAAAElFTkSuQmCC","DE":"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFAAAAAwAgMAAAD7ixVkAAAACVBMVEUAAADdAAD/zgDGIigcAAAAG0lEQVQoz2NgGAVUBaFYwKgg+YKrsIBRQbIFAbpUPtBQ8ZOVAAAAAElFTkSuQmCC","ES":"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFAAAAA1CAMAAADh9px2AAAA3lBMVEX6vQCtFRnnkwabMRKZPA30tQH4uwGXKhDuswC+OxmrqKnjqQOuAyOcSQZ6bh+2TQ6bXAjFlwrvrQTSpyHnnQWzpXigIBCqoY5EZHlqbkeKVBK6ZCKHLxKoggWrWl/Sr0qUFBe8jKamiSDTnhKfUzLjsh/OWwo8MHOrcA6sKxiRdAmyXUfSZauEf1KvjHjccwvLhg+1rZixCiCjFB9BWGODIA7Zggeynaf5vwtvf2zJfwarbly2GxyyiwSuREt5G02qMkCjgCmvl4dxRwB7XgClO0cQP5Wpdl68fpO9fp8nzyHlAAABfklEQVRYw+3Wx26DQBAG4MVb6RhMM8Vg494r7o5byvu/UC5RTrktUpSI/7aXTzPSzGqAUHBACZZgCf4PsFJwwF9OtVBtyyxNbm+L4nDLauFIlq2WXFC300BfXBUxmFZJIWBPWTiC03ccRS+maxktIUWUOmjPj5m6iIFsDAbGQDNmANT2JifY6+HKxkAhzXpXyyKzqMUHsijCupKslaEkTdwbO0W8A2nbRFfu92T4no5SlzXsNp9H5jbRk8djPcxHo9xlDYkT3JxfxL6iackwl0apKwh9EXMtyTF+24jrgZZ0L+lH6naCuN/hqlC8HTr6Mgy7q1Us5W5NlPgqBDhWpnVKw+7q1TFUVFs8+caGiOcJqUMIl90LRQiyRnyscYmduU3qEEIEVUNTEWtIAeYemy9QrSNkco+N3Gwyg0KIMlWAKsKnJuemjH2/aYYUoskTITizfM3nA33PGwM5yMa73SGrgKrnedyfLAEAYGYy/P36zRR+OZTnXAmWYAn+lE9C+ywNWkwjFAAAAABJRU5ErkJggg==","FR":"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFAAAAA1BAMAAAAkBnF3AAAAD1BMVEX///8AJlTOESbeYG5Wb42QNrxKAAAAJ0lEQVRIx2MQRAYODEiAWQkZMIwqHFU4qnBU4ajCUYWjCkcVUkEhAIQklyN0REMMAAAAAElFTkSuQmCC","GB-SCT":"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFAAAAAwCAMAAACxOw3FAAAAPFBMVEUAXrje6vb1+f3w9fufw+RrotbU5PP///8Ua76uzOk3gcgCYLn+/v9Ah8t3qtocb8AGYrpHi8zK3fB9rdsuYp5XAAABMElEQVRIx7XXSRaDIAwA0IBKVNCi3P+uXXSQljFpmqVDfP8FQwB8hTqAHYd6pwG8Yrnx0t2WKEmcEHXw9HQ+aCwl5LgjbS4h1f2hfSQ8v69g6M8XkpdPgGn4vqg2nhZxmAAA5tFx3KnWjfPz3pq49d6ot991ol2j+1T3VtBeQXLXtFesptOd0Zo196Dtc+e0tkDpcPdp6+7o87ZXW3Wbt3sz/doON1Vbdjund8vQVte5Ma2V3HJjIzq1tXoztbV6U2pLcZO10W9mZLRXwnSDwGVjp5tHdIJk6aIILxvphZ1pteqHXy/bFPnNIW1f7pf2VW+wilzvxhbgiW7hTUp6GxXe6KVHEeqwdNTXOWecC+VxTnrgFByJ3TCB7NDu8JQ/Vvz14CN9NBM+PPKPt9ZH7jtCXTI1xktAZQAAAABJRU5ErkJggg==","GB-WLS":"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFAAAAAwCAMAAACxOw3FAAAAeFBMVEX///8AsUDIDy3CDiu9DSq0DCi4DSmuCyanCyUArD308/P6+vqdCiIBpjsajTcOmTnfub8qfTXBOlBfSi1xPCzBZHNPXDDmztK0Fi3SmKKGMCunGiu9TmDAGzbr3uDy6eq8JT7KeIbWqrE9bDKbJi2NIyi3MEbMiZSp9FKtAAAFDUlEQVRIx+2Ux3LsOAxFyYtE5Rxa6qDO//+Hs1C37Wf32K8mVM1isBJJ1eHFBUDn/o9/N5JNGb/a/qu84yKbLvl6y/19cfhN+FCWw+FmEqz7JDE53Xh4fpf38nfyTJI7ExEba+Du8MthWYvu1jsO97qLf8btN8euxq29qEJ0GX497FQIu9i55LRlOr7le3hBPgyJc8lRiUSw6xYCLNhHYHzcqQJAt+kWI9RvlMP2BTDZdmV8OpXlaYfxdAcAYWz379kuLASARUyYgOPbTfXtVe7DSMvxEMfx6XYqN9sViO1DY9wRK8AqYkoAgO6pr/4g9hfDd7OJqGqQkIYRbIxdufo03KBMKirCAAAillX+oQZur6szLOVhKE/dPPJykxAEAG/Wu2AqqqoEYhYLIYRtGTvnDjUpLS+BSXwYnHNuvxu7uBMJALrNMXFuP8KESURVzSyIEtXDM19m4cMr4OG2tmlSnw57omAAjrFzLukgBgsmIqZMAHBbq5V02+2NRhq+9t9977ptvHfOuVPsTkKpAeA6di6pyQBllUc5ACqdcy4uy3182NUb2rx4B+Zhy/vtWoN4R5YGYLfpTs4lNTMsiDI9gUvsnOt2RFwfcXTD8etMl1wvu6VeFxshTQOwO7nEuWQrIHmGMgF14lwHEACqh5cPUKzM+pC+Z9I0DQTw0TmX3BgUTFVVRcxCENm7eEF92tTACwMfbUj6sGKjQBqCgk9l4uKNgAj86EAQabh0SbxgW5adAJs/eWW24PLhIIukIRh42J/uWwVREGWV1UI67pPYuTuDiFPg/hoYL89pGgjgNLVgsjABIDFWYlVTAEsZx3HinBuOx+N9AZ3+BLjDYyZLY9LU0sAqxqwcWJUVILZAJMy7envclHG839T4NMj+LSomjIX3PprAaiFVVYKQsbAqVBkAOBgDSgCImQCMlf8Q78Ds0l4hU+R91AKgVIQAVlVliABiBIA1TQF663Bccv8SGLWc91Cd8shXxmymAEAKEUANgAhImI0BYNVLc5/518D82vroAqO5rRpiNlEjEABTgAMBFFTfUGC9tH31CfcRWHjvixkayAyAKrFKAMiYmQKpaUgBALJqnM9faL94uGJHsAZRghDILKhyMGNJTY1FRQQkZCbCRJcXyE9An88AqamakAZLjSSFEFIVFQKmvDdAQMZBCPM5+gHoixGAgITSNBUSZkAgqZEAmAvv874lMpBQSsRT8QPQnwmgIEYWCMzMuDSNMZMCaCPvvY/yqur75gpB016zH4DRBU1VFBqYmATXuS2inAAIgLn6kGJxDdxmefED0Pdj4X0vBmpImyiKvPfNyExKBLo0+ZMZTczTjx56X/XeR1cl9NE8PfKJ8plgagYQNU9IH7j9DWARed+zofH+3L/v9q2YKFN1np7D1is3/meg9z6alHrvfRZ5f27Oz44SE+q9j6KiWKc/cPU9MOqbPPI+6lWfVxfnK7eZj7LqKsLj2Xsftelcee8LU86+BUZZFbitzu3jHfPe+yzP+8ulvbKK0JpsllXjeI6KC+FLTT4p7FsTUQbQZuuveRvGtgkMQKfHWBRXY5V5BHD5XmFVNaIKIp4wT03hvc+zJqjIPI/TtW/y52+TMBOI+dJ8OynZFIjbqsqj8zS3TbQadqmyrCiiakqbRw3OQfsi789Z3qTX/BtgXhVV/vTTr2NWZG+N/Njy0bnKvV8XWfT9pET+b4bz/3D894F/AK8cUFv8OtMJAAAAAElFTkSuQmCC","GB":"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFAAAAAoCAMAAABevo0zAAAAM1BMVEX///+6w9fzytGrtc3WTWM3UInxxMvIEC4BIWnAyNqqtc22wNT0ztTs7vT109n88fPO1OI8OV3ZAAABE0lEQVRIx+3XtxaDMAwF0AfBlFD//2tDDbasYnIYMvAGBpd7WJAEihJbWlezeQHVHuDNn3EZumI5MWvrQyNt0Oe2wyppgSEHlIVB6qBrkYdCRhcoqYEcV7smWnRpoItepnE1lg2VlECWq1dQJ3lQ4A5QIzlQ5E5QJmNQ4XxQIimociHIkyFocBTkyN4He4ObwYZm6jEO5Zxh3C95IMKdfoquIyUeeE8ugdXNecAH/AX8/y+FKw5b9hLBgN/iwRWHuHzB79c5LV9kNy5fKtdxBVYnYXBsC9BIGJzQpGQSBie2UYmEwSmNnidhcOoowpEwOGNYiklE3MVxjpCtxSUMnIQ0uKSR2CctLnFoP0mLS/6tOMgPj+pDAxFVOjwAAAAASUVORK5CYII=","GR":"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFAAAAA1BAMAAAAkBnF3AAAAIVBMVEX///8NXq9Kh8PD1+uGr9fL3e4xdrtnms2lw+GXut11pNKU2lP+AAAAaklEQVRIx2MQBAExBgZWQfyAYRgrFGfACYaCQiUQUAcqBDO0jHEBNG0cuINnKCgEe8kUqAbMsFTCBeDhyDwc4hpVoZgLLjC8sivYS55AhS74AcOwAkpEAgZBIsGQUGhMJBhecT2sopBYhQBrinTBHs9DVgAAAABJRU5ErkJggg==","HU":"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFAAAAAoBAMAAACbTmAyAAAAD1BMVEVHcFDOKTn////zyc3R29PS+FOWAAAAI0lEQVQ4y2MUZCAOMDGMKhwpClmUiFX4fjQcRxPFKBgFhAAALW4BgB9qup8AAAAASUVORK5CYII=","IE":"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFAAAAAoBAMAAACbTmAyAAAAD1BMVEUWm2L/iD7///9jvJb/r33nPMM8AAAAI0lEQVQ4y2NgQAZGSkhARRAZMIwqHFU4qnBU4ajCUYWkKwQAMLBvuQLjteUAAAAASUVORK5CYII=","IT":"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFAAAAA1BAMAAAAkBnF3AAAAD1BMVEXOKzcAkkb///9VtoPecHj7ZEZ0AAAAJklEQVRIx2MQRAZGSkhAhQEFjCocVTiqcFThqMJRhaMKRxVSQSEA6aGUCJuKIGMAAAAASUVORK5CYII=","JP":"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFAAAAA1CAMAAADh9px2AAAAOVBMVEW8AC3ILFHUW3jbdY3DG0PghpvmoLH////kl6n55ur22uC/Czb+/Pzxy9TKNlntu8fPSWnrsb7MP2AZmjhmAAAA40lEQVRYw+3Wyw6EIAwF0PK0vETn/z92Nm6M0rGFZBZy1+SEQCgXlsGBCU7wtWDcvXN+j2PA4BQcUS50g1HDKTr2gR4uwR7QwU2cHNRwGyMFPTSCMrBAM0UCZtsGbRaAHoh4AbhS4MoHI5AJbNDRILLBjQY1G1xp8MMGLQ1aLpjhR/K/d7goGlSjb3ljg4YGHRssNBj5b1mJjpAAUfTyqHlIbHHNoomdWl4qg/8UL/31zOBfr3Ex2NMc6uUcU+3rNsGcyGR+1aUH7Qv1MXmsxv72daAVsYZHS5822DxL+wRfDX4B50xfz1QVWiYAAAAASUVORK5CYII=","KR":"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFAAAAA1CAMAAADh9px2AAAA3lBMVEX///8AR6DNLjoAAADt7e0UFBQODg7p6em3t7fz8vP5+PhXV1egoKBOTk6np6caGhqamppCQkKRkZG8vLzj4+M7OzsJCQm0MEYRRJfAMUNcXFxkZGTHx8evr69xcXGzs7O6y+TRPUjonqRyOWgRU6bV1dVJSUk1NTVtlsnihY2lvt79/P0cRJL0zdDvub4sLCxfX19Gerrca3SQrtZfO3DV4O/XWGGCpNA3QITUcX1cicL21tlUhL/ki5KlMk6/v7+9r8UhX6xxb5+TNVf55edCPn8nTpi2cYnVo7HMzMwEGb/sAAACqUlEQVRYw+2XaXOiQBCGgR5uDUQELxCjxgtjvHJnk72P//+HdoaIjgrMSKVqa6vSVX4Q22d46aH7HUH4iP8imhW+vIrJl3cG4PDkaQBnPHmqDGXDZSId1yiDrHIAcRpqg4dQXhJSPWgjvDSbVwIIfICKppSyk2xFqwD4WHSJxasqYOoWuLoM59lZ51jFECyjeX3JApLUFnjVJijV/GWrAC2dWWkbQHOIYIYY8mCw6FeHUemqB3MiGD/uAXX5qjteLsfdmbFXOsEFSzdBUXMFWzoRXKbS9PGFtImL7hapDn2El28ha2/pY8EOFmufUUK6W1yMnO1UK1qSnwm8vG6R6qq7/aUvpYMYR5ufBmAhomg+zKu0PsfVpQTfSkfxQFfaI5XOf0HlEhYcbL59klKiu3vnA1vWWBsRGTIke+tJSo0rqtKI42X23STrVzrwNqm065/UFqNOQ8q/xVPjawZPGhcE/jwEfev1XuLdWIx3I9ZoWmNdF3H8IBe/FwJ2xDXFq03Ft6jXij7EiSi+HPMwsSHNigLriehaXdxFryDwhtxNj2ydRo/miVPpqVhV+vHf79f34kE0omLARzEjHgruw0kW8PdpHH+4eZejL+m86aZvo+EfDhzdbTrpwM+ndJsg7ofJABil8e6oyVdi9UMdz2OV8izPx7znpHnhjo0/zbyOjWcKHqAmNUSjo3t8jChLYIKsz3PcA5liWHAYUFNv0qdx/RU19cIQ54V5Uy+ey3jlvfFtrLbI/kin5zK2BOX8uUwm2byqtNV9o2Z0VqPFYnHX2Td9gtpWVIZzIJULUSDbAYe3sa0QOUwXSwRzui+Px32R1CafPyRWicMfEjFvhi7fwYbEzIUcDvZEjz3gOQUQU+wyHUZ8ClB4TgHvfk4RBPOdT1If8a/jL1S9MUKKtUGPAAAAAElFTkSuQmCC","LU":"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFAAAAAwAgMAAAD7ixVkAAAACVBMVEUAod7tKTn////17qLaAAAAG0lEQVQoz2MIxQIYRgXJFlyFBYwKki84CqgKAC7hPtCbbnXkAAAAAElFTkSuQmCC","MX":"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFAAAAAuCAMAAACI524uAAAAvVBMVEX////OESYAaEfeYG5Wm4VoPyX8+vL29PFySSzp59vV171SMR2SYjvMzbHi3byxs4nJxaCafFv9/fykqXmFUi6ciG/F39+jbkfAqpKQlVvn7ez779rRsY1zUDg7iIe9v5urekzp1JKnlYx6WT7avGm6qnvMoGEff4LEubT15si/l225h1Bdm53PycPQsVmJtrSyz8t0ra3g0cfPrqp4zON8a2Gux7xCvdQ7d3z3taH0mYzcj56bsLXqj49sj38YYbFcAAABMElEQVRIx+3VRXbFIBQGYCo4JCHuLs9d6vtfVlfwJiWDDvgX8J1z4Qp4fphX8DAvTw8DDGhAAxrw7yBy6zqKTjOBLkV5HAuf+2oekFl5VEdKcAjbOUCXOn2/XnWCQw5Ps7whHpwxKiDhBAp90G1o5axqwaFPfJ8sZihZDiBfCyJURyCMNUGMEGZD3xREkGDbqm4BkBZos+U7k7vdyi84jHF7pdLTAy38ebODZq0Ih0WQtriqtMClBTbT4TvDeNtdSRFIwDItENkyPZZvm7ej2vXbw0dWJVjvlysPZeF+P01lWW6mL+TZmm2DGgeEl0uelz/hcQ+YhbQb2/PS8D6OaryHwE5S/UmhtrUM4yAYDtKqrDlmGTEvcW5nmSQ0m2fBupiy84JKao6UAQ1owP8D/gJ9tyjbzL3r/gAAAABJRU5ErkJggg==","NL":"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFAAAAA1BAMAAAAkBnF3AAAAD1BMVEWuHCj///8hRovIZm5rhLLyO+d3AAAAK0lEQVRIx2NgGAWjYCgCYyIBgyCRYFThqMJBpdCFSMCgRCQYVTiqcDApBADNaJoRWwlNAgAAAABJRU5ErkJggg==","NO":"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFAAAAA6BAMAAADVUMOiAAAAIVBMVEUAIFu6DC/////MSWNBWYV/j6x0haXTZHrGN1T//v7ei5sR6cc6AAAAWklEQVRIx2MQhAMJJTUGBgYnpUJBbIBhVOGowlGFpCk0hgNzqMLFxtgAgxISgCjECjRpoDAUCYQAFbKGYgcMIxO4IAEHIJ/FBTsYyCgkOpmNZtdRhaMKaaMQAO8ZzJXM+UJqAAAAAElFTkSuQmCC","PH":"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFAAAAAoCAMAAABevo0zAAAAk1BMVEX////+6Ib94Wn95Hb+8rr//vT+76vOESYAOKj80RX93VD/++b+65j/9Mb94GD+7aP81Cb/99X91zT7/P5pis3BzurVNUb76uz43ODk6vYQRa7RGy8hUrT08/gHParTJjnpkpyKpNfhaXfaSFnT3PBBar7keobdV2ZUesbspa3ywMWftN720dUyX7n++PnvsrisvuJ0e8aBAAABXElEQVRIx62W6XLCMAyE5Stq7pPQQoCe9KKl7/90DUkMpg3DxNb+9Ey+sVcrRTBrbkgFUD4saIEAdxUtMAT1/EIJDBIJ8NOQAVPfb4GtlWuqG3oshs7KNzIPtWZfNFU29LkgBsKqWtMCna08Y0kCK01eng31KR2sNIFREblbOQAYZ23EkxQUC9LuxLYb9Wu58EAK2UJFrlPZOADDSPAk8wuesEgNZ6XVYDtVOPMPKuKzCFWWwDRWnt8rVtLrDxXIcLqV3aceEzwYgAEXrM+jCrLD8ycOtuvA/Qan6NqTd0+IFkCjKLlZlPkjoh3QiE2qYwPf90u0Beac/wv2R41oDexbLzBa7/YV0QH4dzjMt4juwOP4gvcNUgAhdjFvDOhk3gXgartESqCDeSfg6Uc/uc/GgXoVseizUWDUL0tWfTZ+w26d29eIVMB24aQwz6gyjXlHYElkngbuaiTVLzAfWkblawOMAAAAAElFTkSuQmCC","TR":"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFAAAAA1CAMAAADh9px2AAAASFBMVEXjChfoLDf3trrlFCH1oabpN0L+8fH////mHyvsUVr85ebrSlTwcXjxho32q6/72tztXGXzlZv4wcTykJX++PnqRE7weoH6z9HJeFUyAAAA7ElEQVRYw+2W2RKDIAxFAZFFFhG3///TjmBb21JHIY/cF2dk5pjchESEqqqqqq5LuIUSaxQQThK+ayJtOa6x/CiCC3m4jyBmFyUQVrQrS1x0kUfFK+JRlvBifP2Hda3IB0b/ui9Ck81rY76p0uIsKg28IdlLNAfIAjBpmeRue9wruQw8/+eMYUmZvgU0AWhOPkZyLNRJB1mq/Neaxv28V3u3c32zJgN0hMuJh3OOhzN0lcH7EP6mgN9lNAJPG9SsgbiCzcPnhJ3evVM2sQ87xRsZd4orXXsGduttaQ8T5F4OSG29h/tzqKqqqnoAliYK+q/+x14AAAAASUVORK5CYII=","US":"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFAAAAAqCAMAAAATdiw4AAAAS1BMVEWzGUL///8KMWHsxtDZjKHGU3IMNGMgQ28nSXQ1VX1xXYBgeZiJnLP//v7CzNhGZIgRN2bl6e9RbY+xvc1wh6Prxc+Zqr709vhyX4F3rzwPAAABHklEQVRIx+2UwW7CMBQEzQD77MYkjgmh//+lvUAhFkplK4dWdA5W5rJStKvn+AFXCzYFUNcJwmSUXh+ofgBiBIZelF4fiBKBlAgkyWzp7Ou4OIBu9ODHDnQ+69lhV8fJgWGelOQNw/ulNwRaP4BiFAy9UfqhEgcxILoOEaJQ4Q2lQJgNbA6gadKz0xb4ai4351iJgw7AB7h9Lr2hlOtjLlej9IbZrA+7IRDyaGBjBs2znr2pFMMPKGkwjBCW3hDo+3wfcu49pTdcm2LYhTcdhxANLD6G/e20lbI27IbATJJ8kBKZlMgkcfeG4/DyDj68oRTvgdsjSq8O/PxYp/qXT7tNOW0feNlvysW9Ib+/5c0DjxvzB1o+bMz/cXgHvgD4OyGtUE286gAAAABJRU5ErkJggg==","VA":"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFAAAABQCAMAAAC5zwKfAAABAlBMVEX/8gD////+/v7Qvob5+fn8/PzJtnf19fTaypS9oEDx8fC+vLra19aoqKjKsF7OwpmhfXve3t7o6Ojh1KrXv2+wsbNrIR7u7ern5N+ukjfsvy3m2rLbsSjNzs6zpniniS1pMTPRrz27khyhaWydVlnv5sihoKKmmW7e18OQdyPUzrqymELw69q4pF+CKSeBgILq37vWyqTEqEuagjmUkJDEnR/cycq5rod9foC9tZW1k5KRUlJzODl4eHibmJp5SkCshYfBr3HHxsJVVljj3cnm1JulkE2ail2oOj/Jqapwb3FkZWeIekuFXEO5dXizISeYYGKNiYyjdHaLiHjsy15zYjdH764QAAADEklEQVRYw+3Xx66bQBQG4AtT6GA6xmDcC+6993Z7z/u/SnAUZR2NWSQSs0CCxad/OGeG4e7uLwf1l+MuARMwARMwAf89EKGYwWMtXhAaMow3oTKhYwR5qAmChvjYwAw34dKzPhsLeJ2pU+CCgCvUft/eBNqhRlE6l04P+lyUUAvtm0C6DAxRbcqsInNKT+46KgBdSApGrTyrhwbGtUY6Xf8RXY5YwXo9iyhEAkLZsYP6oHXsZri83Oew3D/qGh7UA1sVGAIQzarZfcCy/MlpAZlLY9DSWIbVg1m2OkEkU4bVluBQrB0pHJcOOG4HWZ6lm9/9KkNWlDInyzWAAez1DdwyZIAUDGo7uSoSVtlZZVt5jAGNsj7ASgtSLMbZ3e7cpYlATZIenxrAZikIHABUwFC6w1YHdc9TSUAkrKeHpxVbnjEZrJSbisEyRkYPnn+cPQxJ2qZjfgxXX7o+ySo9gGig9C55NtO4ZBvumaRtKPHpYEpDHQwks3eESFdc75LVubx7ea6RFUWcVlYHRVf20teaZxoNV98ryvPAI64yxT8eVCbEM2k17LyM6ng2CZvac5Un3xyYKAuClL/OWdYG6L8+VQ5z+wbLvLRzudwaxrVjQ2NUsKzhUGJuBX8BSMwPvMLSGlYO6xD+eUwCNr1eZncSzJ3rLj5zC8mc5A3R9H1JJQSR7I4Ko7xkgvl2u5mnBM+V1tOOKUFCkHFPzZb9fRbEkrNdMqXx6UuwK6po8oRgt1DTjRAUhNIDlVrSwkKYSr7gqx3Sxj4VZCP0uNEmhajtEsLtstOp+IL5uCcEy16zma9sRpEXJeQpOtXZzCWVrxAmpGHeNV7awdmhrmDULNrTx3JjChXCd0hn+o2CVU+PulcwFynacDW1Hj8qPk045bKdal/CTPkKtqOctr+f5l5UTSVfevS89P5eLBbnCyv1+VlclEpbdONaRhCK44fUwirOH8Y8hHEdOFNtO94TbNGKF0Tv7XG8YOm+hOIExbf7a9/EB76+vVnjOMHi/X0xzoT0w+vrOPm9TcAETMAE/H/Bnyo3Y8hn7B0yAAAAAElFTkSuQmCC","VN":"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFAAAAA1BAMAAAAkBnF3AAAALVBMVEX/AAD/6wD/dgD/BwD/LgD/swD/2wD/ywD/lAD/GQD/TAD/ggD/QQD/5AD/aABQeZ7QAAAA3UlEQVQYGe3BMUoDQRiG4RdHTIyy8Im7BjEgOcEUdiLEKoXVlnZubxEhB0hKuzT28QaKF9DGPniBPYrJEILNzvytsM9D6x9xHpveEpvuDJubH2xez7GZ9zFxVeGxOJY+sehKMywOpAcsvqQL4rLhRinlw42aJoel/sgXNMpW2hnUNHNj7UyJcXNt9T1RvUpBsSTOvSi4J8VXWitIulIwIuVIwRspHQUTUm6lvJROSXmXPq6lE1Ke9AjfOiNhX/kCXKkRcXuDmrVsdUlcZ0ownhB35wncM3GeLUerlfALhNEipD22nCoAAAAASUVORK5CYII="};
</script>
<style>
  .fp-h { font: 500 1.5rem/1.3 "Roboto", system-ui, sans-serif; margin: 0 0 1rem; color: var(--global-text-color, #000); }
  .fp {
    --fp-paper: var(--global-bg-color, #ffffff); --fp-card: var(--global-card-bg-color, #ffffff);
    --fp-ink: var(--global-text-color, #000000); --fp-ink-2: var(--global-text-color-light, #828282); --fp-muted: var(--global-text-color-light, #828282);
    --fp-accent: var(--global-theme-color, #b509ac); --fp-home: var(--global-theme-color, #b509ac); --fp-road: var(--global-text-color, #000000);
    --fp-strand: var(--global-divider-color, rgba(0,0,0,0.1));
    --fp-ocean: #f4f4f6; --fp-land: #dedee2; --fp-land-line: #cfcfd5;
    --fp-kr: color-mix(in srgb, var(--fp-accent) 28%, var(--fp-paper)); --fp-us: color-mix(in srgb, var(--fp-accent) 52%, var(--fp-paper)); --fp-uk: color-mix(in srgb, var(--fp-accent) 78%, var(--fp-paper));
    --fp-shadow: 0 0 0 1px var(--global-divider-color, rgba(0,0,0,0.1));
    color: var(--fp-ink); font-family: "Roboto", system-ui, -apple-system, "Segoe UI", sans-serif;
    display: grid; grid-template-columns: minmax(220px, 330px) minmax(250px, 320px) minmax(200px, 1fr); gap: 20px 28px; align-items: start;
  }
  @media (prefers-color-scheme: dark) {
    :root:not([data-theme="light"]) .fp { --fp-ocean: #26262a; --fp-land: #48484e; --fp-land-line: #5a5a61; }
  }
  :root[data-theme="dark"] .fp, html[data-theme="dark"] .fp { --fp-ocean: #26262a; --fp-land: #48484e; --fp-land-line: #5a5a61; }
  @media (max-width: 860px) { .fp { grid-template-columns: 1fr 1fr; } .fp-side { grid-column: 1 / -1; } }
  @media (max-width: 560px) { .fp { grid-template-columns: 1fr; } }

  .fp-globe { width: 100%; aspect-ratio: 1; touch-action: none; cursor: grab; overflow: hidden; border-radius: 50%; background: var(--fp-card); box-shadow: var(--fp-shadow); display: block; }
  .fp-globe:active { cursor: grabbing; }
  .fp-globe .sphere { fill: var(--fp-ocean); }
  .fp-globe .land { fill: var(--fp-land); stroke: var(--fp-land-line); stroke-width: .7; stroke-linejoin: round; }
  .fp-globe .visit { fill: var(--fp-accent); fill-opacity: .4; }
  .fp-globe .visit.on { fill-opacity: 1; stroke: var(--fp-card); stroke-width: 1.5; }
  .fp-globe .home { fill: var(--fp-card); stroke: var(--fp-home); stroke-width: 2.5; }
  .fp-globe .home.on { fill: var(--fp-home); }
  .fp-globe .arc { fill: none; stroke: var(--fp-accent); stroke-width: 1.6; stroke-dasharray: 3 4; stroke-linecap: round; }
  .fp-globe .road { fill: none; stroke: var(--fp-road); stroke-width: 2.4; stroke-linecap: round; stroke-linejoin: round; }
  .fp-globe .plane { fill: var(--fp-card); stroke: var(--fp-ink); stroke-width: 1.3; stroke-linejoin: round; }
  .fp-globe .car { fill: var(--fp-road); stroke: var(--fp-card); stroke-width: 1; }
  .fp-globe .plabel { font: 500 10.5px/1 "Roboto", sans-serif; fill: var(--fp-ink); paint-order: stroke; stroke: var(--fp-card); stroke-width: 3px; stroke-linejoin: round; pointer-events: none; }
  .fp-globe .tag rect { fill: var(--fp-card); stroke: var(--fp-ink); stroke-width: 1.2; }
  .fp-globe .tag text { font: 500 12.5px/1 "Roboto", sans-serif; fill: var(--fp-ink); }

  .fp-dna { height: 520px; overflow-y: auto; overflow-x: hidden; scrollbar-width: thin; border-radius: 8px; }
  .fp-dna svg { display: block; width: 100%; height: auto; font-family: "Roboto", sans-serif; }
  .fp-dna .strand { fill: none; stroke-width: 5; stroke-linecap: round; }
  .fp-dna .strand.b { stroke: var(--fp-strand); }
  .fp-dna .rung { stroke-width: 2.5; stroke-linecap: round; opacity: .55; }
  .fp-dna .bub { cursor: pointer; }
  .fp-dna .bub circle.body { fill: var(--fp-card); filter: url(#fp-sh); }
  .fp-dna .bub:hover circle.body, .fp-dna .bub.on circle.body { stroke: var(--fp-accent); stroke-width: 3; }
  .fp-dna .bub text { font: 500 8.5px/1 "Roboto", sans-serif; letter-spacing: .05em; fill: var(--fp-ink); text-anchor: middle; pointer-events: none; }
  .fp-dna .bub .sat { fill: var(--fp-accent); }
  .fp-dna .when { font: 500 9.5px/1 "Roboto", sans-serif; fill: var(--fp-ink-2); pointer-events: none; }
  .fp-dna .note { font: 400 8.5px/1 "Roboto", sans-serif; fill: var(--fp-muted); pointer-events: none; }
  .fp-dna .pill { cursor: pointer; }
  .fp-dna .pill rect { stroke: var(--fp-card); stroke-width: 2; filter: url(#fp-sh); }
  .fp-dna .pill:hover rect, .fp-dna .pill.on rect { stroke: var(--fp-accent); }
  .fp-dna .pill .city { font: 500 11.5px/1 "Roboto", sans-serif; fill: var(--fp-ink); pointer-events: none; }
  .fp-dna .pill .yrs { font: 500 9px/1 "Roboto", sans-serif; fill: var(--fp-ink-2); pointer-events: none; letter-spacing: .03em; }
  .fp-dna [tabindex]:focus-visible { outline: 3px solid var(--fp-accent); outline-offset: 3px; border-radius: 50%; }

  .fp-side { position: relative; display: grid; grid-template-columns: 132px 1fr; gap: 12px; align-items: start; }
  .fp-chr { width: 132px; height: auto; display: block; overflow: visible; font-family: "Roboto", sans-serif; }
  .fp-chr .outline { fill: var(--fp-card); stroke: var(--fp-ink); stroke-width: 1.8; }
  .fp-chr .band { fill: var(--fp-ink); cursor: pointer; }
  .fp-chr .band.lt { fill: var(--fp-card); }
  .fp-chr .band:hover, .fp-chr .band.on { fill: var(--fp-accent); }
  .fp-chr .sep { stroke: var(--fp-ink); stroke-width: 1; }
  .fp-chr .bl { font: 500 10px/1 "Roboto", sans-serif; fill: var(--fp-muted); pointer-events: none; }
  .fp-chr .bn { font: 500 11px/1 "Roboto", sans-serif; fill: var(--fp-ink); cursor: pointer; }
  .fp-chr .bn:hover, .fp-chr .bn.on { fill: var(--fp-accent); }
  .fp-chr .tick { stroke: var(--fp-ink); stroke-width: 1; }
  .fp-card { position: absolute; left: 144px; right: 0; top: 0; display: grid; gap: 4px; padding: 10px 12px; border-radius: 8px; background: var(--fp-card); border: 1px solid var(--global-divider-color, rgba(0,0,0,0.1)); transition: top .25s; }
  .fp-card::before { content: ""; position: absolute; left: -7px; top: 50%; width: 12px; height: 12px; margin-top: -6px; background: var(--fp-card); border-left: 1px solid var(--global-divider-color, rgba(0,0,0,0.1)); border-bottom: 1px solid var(--global-divider-color, rgba(0,0,0,0.1)); transform: rotate(45deg); }
  @media (prefers-reduced-motion: reduce) { .fp-card { transition: none; } }
  .fp-card b { font-size: 14px; font-weight: 500; }
  .fp-card p { margin: 0; font-size: 12.5px; line-height: 1.5; color: var(--fp-ink-2); }
  .fp-card .play { all: unset; cursor: pointer; color: var(--fp-accent); border-bottom: 1px dotted var(--fp-accent); font: inherit; }
  .fp-card .play::before { content: "B6"; font-size: 8px; margin-right: 4px; vertical-align: 1px; }
  .fp-card a.play { text-decoration: none; }
  .fp-card .play:hover, .fp-card .play.on { border-bottom-style: solid; }
  .fp-card .play:focus-visible { outline: 2px solid var(--fp-accent); outline-offset: 2px; border-radius: 3px; }
  .fp-card .player { display: block; }
  .fp-card .player iframe { display: block; width: 100%; height: 152px; border: 0; border-radius: 8px; margin-top: 10px; }
</style>

<h2 class="fp-h">Footprints</h2>
<div class="fp" id="fp">
  <svg class="fp-globe" id="fp-globe" viewBox="0 0 400 400" role="img" aria-label="Globe turned to the selected place"></svg>
  <div class="fp-dna" id="fp-dna"></div>
  <div class="fp-side">
    <svg class="fp-chr" id="fp-chr" viewBox="0 0 132 470" role="img" aria-label="My interests drawn as one chromosome"></svg>
    <div class="fp-card" id="fp-card"></div>
  </div>
</div>

<script>
(function () {
  const HOMES = [
    { city: 'Suwon',    cc: 'KR', lat: 37.263, lon: 127.028, start: 2003, end: 2006 },
    { city: 'New York', cc: 'US', lat: 40.750, lon: -74.000, start: 2007, end: 2008 },
    { city: 'Seoul',    cc: 'KR', lat: 37.566, lon: 126.978, start: 2009, end: 2010 },
    { city: 'London',   cc: 'GB', lat: 51.507, lon:  -0.128, start: 2011, end: 2015 },
    { city: 'Seoul',    cc: 'KR', lat: 37.566, lon: 126.978, start: 2016, end: 2026, present: true },
  ];
  // [place, cc, lat, lon, when, groupKey?]
  const RAW = [
    ['Cancún','MX',21.1619,-86.8515,'2008.02'],
    ['Baltimore','US',39.2904,-76.6122,'2007–2008'],['Cambridge','US',42.3736,-71.1097,'2007–2008'],
    ['Boston','US',42.3601,-71.0589,'2007–2008'],['Thousand Islands','US',44.33,-75.9538,'2007–2008'],
    ['Montauk','US',41.0362,-71.9543,'2007–2008'],['Orlando','US',28.3852,-81.5639,'2007–2008'],
    ['Longwood Gardens','US',39.8719,-75.6764,'2007–2008'],['Bear Mountain','US',41.3128,-73.9888,'2007–2008'],
    ['Bronx','US',40.8448,-73.8648,'2007–2008'],['Atlanta','US',33.749,-84.388,'2007–2008'],
    ['Grand Canyon','US',36.1069,-112.1129,'2007–2008'],['Las Vegas','US',36.1699,-115.1398,'2007–2008'],
    ['San Francisco','US',37.7749,-122.4194,'2007–2008'],
    ['Rome','IT',41.9028,12.4964,'2013.04'],['Vatican City','VA',41.9029,12.4534,'2013.04'],
    ['Zurich','CH',47.3769,8.5417,'2013.08'],['Nice','FR',43.7102,7.262,'2013.08'],['Oslo','NO',59.9139,10.7522,'2013.08'],
    ['Budapest','HU',47.4979,19.0402,'2013.09'],['Paris','FR',48.8566,2.3522,'2013.11'],
    ['Berlin','DE',52.52,13.405,'2011–2015'],['Amsterdam','NL',52.3676,4.9041,'2011–2015'],
    ['Brussels','BE',50.8503,4.3517,'2011–2015'],['Luxembourg City','LU',49.6116,6.1319,'2011–2015'],
    ['Madrid','ES',40.4168,-3.7038,'2014.08'],['Istanbul','TR',41.0082,28.9784,'2014.10'],['Athens','GR',37.9838,23.7275,'2014.10'],
    ['Dublin','IE',53.3498,-6.2603,'2015.04'],['Normandy','FR',49.1829,-0.3707,'2015.05'],
    ['Wales','GB-WLS',52.13,-3.78,'2011–2015'],['Scotland','GB-SCT',55.95,-3.19,'2011–2015'],
    ['Ho Chi Minh City','VN',10.8231,106.6297,'2022.12'],['Tokyo','JP',35.6762,139.6503,'2023.01'],['Osaka','JP',34.6937,135.5023,'2023.01'],
    ['Cebu','PH',10.3157,123.8854,'2023.06'],['Tokyo','JP',35.6762,139.6503,'2023.07'],
    ['Dallas','US',32.7767,-96.797,'2024.08','ex'],['Austin','US',30.2672,-97.7431,'2024.08','ex'],
    ['Albuquerque','US',35.0844,-106.6504,'2024.11','ex'],['Grand Canyon','US',36.1069,-112.1129,'2024.11','ex'],
    ['Zion Canyon','US',37.2982,-113.0263,'2024.11','ex'],['Las Vegas','US',36.1699,-115.1398,'2024.11','ex'],
    ['Hoover Dam','US',36.0161,-114.7377,'2024.11','ex'],['Phoenix','US',33.4484,-112.074,'2024.11','ex'],
    ['White Sands','US',32.7791,-106.1719,'2024.11','ex'],['El Paso','US',31.7619,-106.485,'2024.11','ex'],
    ['Chicago','US',41.8781,-87.6298,'2024.12','ex'],['Washington DC','US',38.9072,-77.0369,'2024.12','ex'],['New York','US',40.7128,-74.006,'2024.12','ex'],
    ['Montreal','CA',45.5019,-73.5674,'2026.10'],
  ];
  const GROUP_META = { ex: { when: 'Aug–Dec 2024', note: 'Exchange student', road: [
    [-96.797, 32.7767], [-101.83, 35.22], [-106.6504, 35.0844], [-112.1129, 36.1069], [-112.99, 37.20], [-115.1398, 36.1699],
    [-114.7377, 36.0161], [-112.074, 33.4484], [-106.78, 32.31], [-106.1719, 32.7791], [-106.485, 31.7619], [-96.797, 32.7767],
  ] } };
  const MON = ['Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec'];
  const code = cc => ({ GB: 'UK', 'GB-WLS': 'WLS', 'GB-SCT': 'SCT' })[cc] || cc;
  const river = cc => ({ KR: 'var(--fp-kr)', US: 'var(--fp-us)', GB: 'var(--fp-uk)' })[cc];
  const whenLabel = w => w.includes('.') ? `${MON[+w.slice(5) - 1]} ${w.slice(0, 4)}` : `${w.slice(0, 4)}–${w.slice(7)}`;
  const whenNum = w => w.includes('.') ? +w.slice(0, 4) + (+w.slice(5) - 1) / 12 : +w.slice(0, 4) - 0.5;

  const TRIPS = RAW.map(([place, cc, lat, lon, when, g]) => {
    const yr = +when.slice(0, 4);
    return { place, cc, lat, lon, when, g, era: HOMES.findIndex(h => yr >= h.start && yr <= h.end) };
  });
  const groups = d3.groups(TRIPS, t => t.g ? `${t.era}|${t.g}` : `${t.era}|${t.cc}|${t.when}`).map(([, pts]) => {
    const m = pts[0].g ? GROUP_META[pts[0].g] : null;
    return { era: pts[0].era, cc: pts[0].cc, pts, when: m ? m.when : whenLabel(pts[0].when), note: m ? m.note : '', road: m ? m.road : null,
      lon: d3.mean(pts, p => p.lon), lat: d3.mean(pts, p => p.lat), t: d3.min(pts, p => whenNum(p.when)) };
  }).sort((a, b) => a.era - b.era || a.t - b.t);

  // ---- DNA timeline: vertical double helix, ordinal slots ----
  const items = [];
  HOMES.forEach((h, i) => { items.push({ kind: 'home', i, h, w: 54 }); groups.forEach((g, gi) => { if (g.era === i) items.push({ kind: 'trip', gi, g, w: 46 }); }); });
  let cursor = 16; items.forEach(it => { it.y = cursor + it.w / 2; cursor += it.w; });
  const Hd = cursor + 16, Wd = 300, cx = 150, A = 34, P = 400;
  const xA = y => cx + A * Math.sin(2 * Math.PI * y / P), xB = y => cx - A * Math.sin(2 * Math.PI * y / P);
  const eraSpan = i => { const s0 = items.find(it => it.kind === 'home' && it.i === i).y - 27; const n = items.find(it => it.kind === 'home' && it.i === i + 1); return [s0, n ? n.y - 27 : Hd - 16]; };
  const strand = (fx, y0, y1) => 'M' + d3.range(y0, y1 + 0.01, 4).map(y => `${fx(y).toFixed(1)},${y.toFixed(1)}`).join(' L');
  let s = `<svg viewBox="0 0 ${Wd} ${Hd}"><defs><filter id="fp-sh" x="-30%" y="-30%" width="160%" height="160%"><feDropShadow dx="0" dy="1" stdDeviation="1.2" flood-color="#000" flood-opacity=".12"/></filter></defs>`;
  HOMES.forEach((h, i) => { const [y0, y1] = eraSpan(i); s += `<path class="strand b" d="${strand(xB, y0, y1)}"/><path class="strand" stroke="${river(h.cc)}" d="${strand(xA, y0, y1)}"/>`; });
  let alt = 0;
  items.forEach(it => {
    if (it.kind === 'home') {
      const h = it.h, y = it.y, w = 112, hh = 28;
      s += `<g class="pill" data-h="${it.i}" tabindex="0"><rect x="${cx - w / 2}" y="${y - hh / 2}" width="${w}" height="${hh}" rx="17" fill="${river(h.cc)}"/>`;
      s += `<image href="${FLAGS[h.cc]}" x="${cx - w / 2 + 8}" y="${y - 7}" width="21" height="14" preserveAspectRatio="xMidYMid slice"/>`;
      s += `<text class="city" x="${cx - w / 2 + 36}" y="${y - 2}">${h.city}</text><text class="yrs" x="${cx - w / 2 + 36}" y="${y + 9}">${h.start}–${h.present ? 'now' : String(h.end).slice(2)}</text></g>`;
      return;
    }
    const g = it.g, y = it.y, n = g.pts.length, d = Math.min(44, 32 + (n - 1) * 1.2), r = d / 2;
    alt ^= 1; const x = alt ? xA(y) : xB(y), xo = alt ? xB(y) : xA(y);
    s += `<line class="rung" x1="${x}" y1="${y}" x2="${xo}" y2="${y}" stroke="${river(HOMES[g.era].cc)}"/>`;
    s += `<g class="bub" data-g="${it.gi}" tabindex="0"><circle class="body" cx="${x}" cy="${y}" r="${r}"/>`;
    s += `<image href="${FLAGS[g.cc]}" x="${x - d * .24}" y="${y - d * .3}" width="${d * .48}" height="${d * .32}" preserveAspectRatio="xMidYMid slice"/>`;
    s += `<text x="${x}" y="${y + d * .26}">${code(g.cc)}</text>`;
    if (n > 1) d3.range(n).forEach(k => { const a = -Math.PI / 2 + k * 2 * Math.PI / n; s += `<circle class="sat" cx="${(x + (r + 1) * Math.cos(a)).toFixed(1)}" cy="${(y + (r + 1) * Math.sin(a)).toFixed(1)}" r="2.2"/>`; });
    s += '</g>';
    const right = x >= cx, lx = right ? x + r + 8 : x - r - 8, anchor = right ? 'start' : 'end';
    s += `<text class="when" x="${lx}" y="${y + (g.note ? -2 : 4)}" text-anchor="${anchor}">${g.when}</text>`;
    if (g.note) s += `<text class="note" x="${lx}" y="${y + 11}" text-anchor="${anchor}">${g.note}</text>`;
  });
  s += '</svg>';
  const dna = document.getElementById('fp-dna');
  dna.innerHTML = s;

  // ---- globe ----
  const gsvg = d3.select('#fp-globe');
  const R = 186, C = 200;
  const proj = d3.geoOrthographic().scale(R).translate([C, C]).clipAngle(90).precision(.5);
  const path = d3.geoPath(proj);
  const gSphere = gsvg.append('path').attr('class', 'sphere').datum({ type: 'Sphere' });
  const gLand = gsvg.append('path').attr('class', 'land');
  const gArc = gsvg.append('path').attr('class', 'arc');
  const gRoad = gsvg.append('path').attr('class', 'road');
  const gVisit = gsvg.append('g'), gHome = gsvg.append('g'), gLabels = gsvg.append('g');
  const gTag = gsvg.append('g').attr('class', 'tag').style('display', 'none');
  gTag.append('rect').attr('rx', 9).attr('height', 24);
  gTag.append('image').attr('x', 8).attr('y', 5).attr('width', 21).attr('height', 14);
  gTag.append('text').attr('y', 16.5).attr('x', 35);
  const gPlane = gsvg.append('path').attr('class', 'plane').style('display', 'none')
    .attr('d', 'M-11,-2 L11,-9 L3,11 L-1,2 Z M-1,2 L11,-9 M-11,-2 L-1,2');
  const gCar = gsvg.append('path').attr('class', 'car').style('display', 'none')
    .attr('d', 'M-9,2 l2.5,-5 h9 l4,5 h2.5 v4 h-2 a2,2 0 0 1 -4,0 h-6 a2,2 0 0 1 -4,0 h-2 z');
  let land = null, arcGeo = null, roadGeo = null, tag = null, onSet = new Set(), onHome = -1, center = null, labels = [];

  const vis = p => d3.geoDistance([p.lon, p.lat], [-proj.rotate()[0], -proj.rotate()[1]]) < Math.PI / 2 - 0.01;
  function placeLabels() {
    if (proj.scale() < R * 1.2) return [];
    const dots = [...onSet].filter(vis).map(d => proj([d.lon, d.lat]));
    const boxes = [], out = [];
    const hit = b => boxes.some(o => b[0] < o[2] && b[2] > o[0] && b[1] < o[3] && b[3] > o[1])
      || dots.some(([dx, dy]) => dx + 5 > b[0] && dx - 5 < b[2] && dy + 5 > b[1] && dy - 5 < b[3]);
    labels.filter(vis).forEach(d => {
      const [px, py] = proj([d.lon, d.lat]), w = d.place.length * 6.2 + 8, h = 14;
      const cands = [
        [px + 8, py + 3.5, 'start', [px + 8, py - h / 2, px + 8 + w, py + h / 2]],
        [px - 8, py + 3.5, 'end', [px - 8 - w, py - h / 2, px - 8, py + h / 2]],
        [px, py - 9, 'middle', [px - w / 2, py - 9 - h + 3, px + w / 2, py - 9 + 3]],
        [px, py + 16, 'middle', [px - w / 2, py + 16 - h + 3, px + w / 2, py + 16 + 3]],
      ];
      for (const [x, y, anchor, box] of cands) { if (!hit(box)) { boxes.push(box); out.push({ d, x, y, anchor }); break; } }
    });
    return out;
  }
  function redraw() {
    gSphere.attr('d', path);
    if (land) gLand.attr('d', path(land));
    gArc.attr('d', arcGeo ? path(arcGeo) : null);
    gRoad.attr('d', roadGeo ? path(roadGeo) : null);
    gVisit.selectAll('circle').data(TRIPS.filter(vis)).join('circle')
      .attr('class', d => 'visit' + (onSet.has(d) ? ' on' : ''))
      .attr('r', d => onSet.has(d) ? 4.5 : 2.6)
      .attr('cx', d => proj([d.lon, d.lat])[0]).attr('cy', d => proj([d.lon, d.lat])[1]);
    gHome.selectAll('circle').data(HOMES.filter(vis)).join('circle')
      .attr('class', d => 'home' + (HOMES.indexOf(d) === onHome ? ' on' : ''))
      .attr('r', d => HOMES.indexOf(d) === onHome ? 6.5 : 4.5)
      .attr('cx', d => proj([d.lon, d.lat])[0]).attr('cy', d => proj([d.lon, d.lat])[1]);
    gLabels.selectAll('text').data(placeLabels()).join('text').attr('class', 'plabel')
      .attr('x', l => l.x).attr('y', l => l.y).attr('text-anchor', l => l.anchor).text(l => l.d.place);
    if (tag && vis(tag)) {
      const [px, py] = proj([tag.lon, tag.lat]);
      gTag.style('display', null).attr('transform', `translate(${px + 12},${py - 32})`);
      gTag.select('image').attr('href', FLAGS[tag.cc]);
      gTag.select('text').text(tag.label);
      gTag.select('rect').attr('width', gTag.select('text').node().getComputedTextLength() + 45);
    } else gTag.style('display', 'none');
  }
  let spin = null;
  function stopSpin() { if (spin) { spin.stop(); spin = null; } }
  function shortest(r0, lon, lat) { let dl = -lon - r0[0]; dl = ((dl + 540) % 360) - 180; return [r0[0] + dl, -lat, 0]; }
  const fitScale = pts => {
    const c = [d3.mean(pts, p => p.lon), d3.mean(pts, p => p.lat)];
    const maxD = d3.max(pts, p => d3.geoDistance(c, [p.lon, p.lat])) || 0;
    return Math.max(R * 1.25, Math.min(R * 2.1, 150 / Math.sin(Math.max(maxD, 0.02))));
  };

  function driveRoad(coords) {
    const segs = d3.pairs(coords), lens = segs.map(([a, b]) => d3.geoDistance(a, b)), total = d3.sum(lens);
    gCar.style('display', null);
    gsvg.transition('road').duration(3200).ease(d3.easeSinInOut).tween('road', () => t => {
      let left = t * total, pts = [coords[0]], pos = coords[0], dir = coords[1];
      for (let i = 0; i < segs.length; i++) {
        if (left >= lens[i]) { pts.push(segs[i][1]); left -= lens[i]; continue; }
        const k = left / lens[i]; pos = d3.geoInterpolate(segs[i][0], segs[i][1])(k); dir = segs[i][1]; pts.push(pos); break;
      }
      roadGeo = { type: 'LineString', coordinates: pts };
      const [ax, ay] = proj(pos), [bx, by] = proj(dir);
      gCar.attr('transform', `translate(${ax},${ay}) rotate(${Math.atan2(by - ay, bx - ax) * 180 / Math.PI}) scale(${bx < ax ? '1,-1' : '1,1'})`);
      redraw();
    }).on('end', () => gCar.style('display', 'none'));
  }

  function fly(lon, lat, scale, { after = null, plane = true } = {}) {
    stopSpin(); gsvg.interrupt('fly'); gsvg.interrupt('road'); gCar.style('display', 'none'); roadGeo = null;
    const r0 = proj.rotate(), r1 = shortest(r0, lon, lat), s0 = proj.scale();
    const from = center || [-r0[0], -r0[1]];
    const geo = d3.geoInterpolate(from, [lon, lat]);
    const hop = plane && (Math.abs(from[0] - lon) > 0.01 || Math.abs(from[1] - lat) > 0.01);
    center = [lon, lat];
    if (matchMedia('(prefers-reduced-motion: reduce)').matches) { proj.rotate(r1).scale(scale); arcGeo = hop ? { type: 'LineString', coordinates: [from, [lon, lat]] } : null; redraw(); if (after) after(); return; }
    const dur = hop ? 1500 : 700, dipTo = R * 0.92;
    gPlane.style('display', hop ? null : 'none');
    gsvg.transition('fly').duration(dur).ease(d3.easeCubicInOut)
      .tween('fly', () => {
        const rot = d3.interpolate(r0, r1);
        return t => {
          proj.rotate(rot(t));
          const dip = hop ? Math.sin(Math.PI * t) : 0;
          proj.scale(s0 + (scale - s0) * t - dip * Math.max(0, Math.min(s0, scale) - dipTo));
          if (hop) {
            arcGeo = { type: 'LineString', coordinates: d3.range(0, 1.0001, 0.02).filter(k => k <= t).map(geo) };
            const p = geo(t), q = geo(Math.min(1, t + 0.01));
            const [ax, ay] = proj(p), [bx, by] = proj(q);
            gPlane.attr('transform', `translate(${ax},${ay}) rotate(${Math.atan2(by - ay, bx - ax) * 180 / Math.PI + 18}) scale(${1 + 0.6 * dip})`);
          }
          redraw();
        };
      })
      .on('end', () => { gPlane.style('display', 'none'); if (after) after(); });
  }
  gsvg.call(d3.drag().clickDistance(4).on('start', () => { stopSpin(); gsvg.interrupt('fly'); gPlane.style('display', 'none'); }).on('drag', e => {
    const r = proj.rotate(), k = 75 / proj.scale();
    proj.rotate([r[0] + e.dx * k, Math.max(-90, Math.min(90, r[1] - e.dy * k)), 0]); redraw();
  }));
  // click on the globe: zoom in step by step on that point; at max zoom, click resets
  const ZMAX = R * 6;
  gsvg.on('click', e => {
    const geo = proj.invert(d3.pointer(e, gsvg.node()));
    if (!geo) return;
    if (proj.scale() >= ZMAX - 1) fly(-proj.rotate()[0], -proj.rotate()[1], R, { plane: false });
    else fly(geo[0], geo[1], Math.min(ZMAX, Math.max(R * 2.2, proj.scale() * 1.7)), { plane: false });
  });

  // ---- selection ----
  function clearOn() { dna.querySelectorAll('.on').forEach(n => n.classList.remove('on')); }
  function reveal(el) { el.scrollIntoView({ behavior: matchMedia('(prefers-reduced-motion: reduce)').matches ? 'auto' : 'smooth', block: 'center', inline: 'nearest' }); }
  function selectHome(i) {
    const h = HOMES[i]; clearOn(); const el = dna.querySelector(`[data-h="${i}"]`); el.classList.add('on'); reveal(el);
    onSet = new Set(TRIPS.filter(t => t.era === i)); onHome = i; labels = [];
    tag = { lon: h.lon, lat: h.lat, cc: h.cc, label: h.city };
    fly(h.lon, h.lat, R * 1.6);
  }
  function selectGroup(gi) {
    const g = groups[gi]; clearOn(); const el = dna.querySelector(`[data-g="${gi}"]`); el.classList.add('on'); reveal(el);
    onSet = new Set(g.pts); onHome = g.era; labels = g.pts.length > 1 ? g.pts : [];
    tag = g.pts.length === 1 ? { lon: g.lon, lat: g.lat, cc: g.cc, label: g.pts[0].place } : null;
    fly(g.lon, g.lat, fitScale(g.pts), { after: g.road ? () => driveRoad(g.road) : null });
  }
  const act = el => { if (!el) return; if (el.dataset.h !== undefined) selectHome(+el.dataset.h); else selectGroup(+el.dataset.g); };
  dna.addEventListener('click', e => act(e.target.closest('[data-h],[data-g]')));
  dna.addEventListener('keydown', e => { if (e.key === 'Enter' || e.key === ' ') { e.preventDefault(); act(e.target.closest('[data-h],[data-g]')); } });

  function start(topo) {
    land = topojson.feature(topo, topo.objects.land);
    const h = HOMES[HOMES.length - 1];
    proj.rotate([-h.lon + 40, -h.lat + 10, 0]);
    onHome = HOMES.length - 1;
    redraw();
    if (!matchMedia('(prefers-reduced-motion: reduce)').matches) {
      let last = 0;
      spin = d3.timer(el => { const r = proj.rotate(); proj.rotate([r[0] + (el - last) * 0.008, r[1], 0]); last = el; redraw(); });
    }
  }
  const inline = document.getElementById('fp-land');
  if (inline) start(JSON.parse(inline.textContent));
  else fetch('/assets/json/land-110m.json').then(r => r.json()).then(start);

  // ---- one chromosome, one band per interest ----
  const BANDS = [
    { id: 'sport', arm: 'p', label: 'p11', name: 'Sports',    text: 'A swimmer, and a Taekwondo black belt.' },
    { id: 'piano', arm: 'q', label: 'q11', name: 'Piano',     text: 'I hold ABRSM (Associated Board of the Royal Schools of Music) Grade 8 in piano.' },
    { id: 'pop',   arm: 'q', label: 'q12', name: 'Pop music', text: 'I like to find hidden gems. Lately on repeat: <button class="play" data-sp="654XTpkoachnc4HT2Fi3Fn">flowerovlove</button>, <button class="play" data-sp="6vhPYadsf8JILPYYuuCqya">GLADES</button><span class="player" id="fp-player"></span>' },
    { id: 'story', arm: 'q', label: 'q21', name: 'Stories',   text: 'I love reading classic novels (especially Hermann Hesse) and watching well-made documentaries or series that stay with me long after the credits.' },
  ];
  const CX = 100, HW = 24, TOP = 22, CEN = 150, BOT = 440, WAIST = 9, NECK = 26;
  // outline: rounded telomeres, pinched centromere (one continuous body)
  const outline = `M${CX - HW},${TOP + HW} A${HW},${HW} 0 0 1 ${CX + HW},${TOP + HW} L${CX + HW},${CEN - NECK} C${CX + HW},${CEN - 6} ${CX + WAIST},${CEN - 8} ${CX + WAIST},${CEN} C${CX + WAIST},${CEN + 8} ${CX + HW},${CEN + 6} ${CX + HW},${CEN + NECK} L${CX + HW},${BOT - HW} A${HW},${HW} 0 0 1 ${CX - HW},${BOT - HW} L${CX - HW},${CEN + NECK} C${CX - HW},${CEN + 6} ${CX - WAIST},${CEN + 8} ${CX - WAIST},${CEN} C${CX - WAIST},${CEN - 8} ${CX - HW},${CEN - 6} ${CX - HW},${CEN - NECK} Z`;
  // band rows: [y0, y1, id|null] — dark/light G-banding with unlabelled filler bands, like a real ideogram
  const rows = [
    [TOP + 10, TOP + 30, null], [TOP + 30, TOP + 80, 'sport'], [TOP + 80, CEN - 30, null],
    [CEN + 30, CEN + 60, null], [CEN + 60, CEN + 104, 'piano'], [CEN + 104, CEN + 124, null], [CEN + 124, CEN + 162, 'pop'],
    [CEN + 162, CEN + 192, null], [CEN + 192, CEN + 246, 'story'], [CEN + 246, BOT - 12, null],
  ];
  let c = `<defs><clipPath id="fp-cc"><path d="${outline}"/></clipPath></defs><path class="outline" d="${outline}"/>`;
  rows.forEach(([y0, y1, id], i) => {
    const b = id && BANDS.find(d => d.id === id), dark = i % 2 === 0;
    c += `<rect class="band ${dark ? '' : 'lt'}" ${b ? `data-b="${id}" tabindex="0"` : ''} x="${CX - HW}" y="${y0}" width="${HW * 2}" height="${y1 - y0}" clip-path="url(#fp-cc)"/>`;
    c += `<line class="sep" x1="${CX - HW}" x2="${CX + HW}" y1="${y0}" y2="${y0}" clip-path="url(#fp-cc)"/>`;
    if (b) {
      Object.assign(b, { y0, y1 });
      c += `<text class="bn" data-b="${id}" x="${CX - HW - 10}" y="${(y0 + y1) / 2 - 1}" text-anchor="end">${b.name}</text>`;
      c += `<text class="bl" x="${CX - HW - 10}" y="${(y0 + y1) / 2 + 11}" text-anchor="end">${b.label}</text>`;
      c += `<line class="tick" x1="${CX + HW}" x2="${CX + HW + 8}" y1="${(y0 + y1) / 2}" y2="${(y0 + y1) / 2}"/>`;
    }
  });
  c += `<text class="bl" x="${CX - HW - 10}" y="${TOP + 4}" text-anchor="end">p</text><text class="bl" x="${CX - HW - 10}" y="${BOT}" text-anchor="end">q</text>`;
  const chr = document.getElementById('fp-chr'); chr.innerHTML = c;
  const card = document.getElementById('fp-card'), side = card.parentElement;
  let curBand = 'piano';
  function placeCard() {
    const el = chr.querySelector(`rect[data-b="${curBand}"]`); if (!el) return;
    const r = el.getBoundingClientRect(), sr = side.getBoundingClientRect();
    const top = r.top - sr.top + r.height / 2 - card.offsetHeight / 2;
    card.style.top = Math.max(0, Math.min(sr.height - card.offsetHeight, top)) + 'px';
  }
  function showBand(id) {
    const b = BANDS.find(d => d.id === id); curBand = id;
    chr.querySelectorAll('[data-b]').forEach(n => n.classList.toggle('on', n.dataset.b === id));
    card.innerHTML = `<b>${b.name}</b><p>${b.text}</p>`;
    placeCard();
  }
  addEventListener('resize', placeCard);
  chr.addEventListener('click', e => { const n = e.target.closest('[data-b]'); if (n) showBand(n.dataset.b); });
  card.addEventListener('click', e => {
    const b = e.target.closest('.play'); if (!b) return;
    card.querySelectorAll('.play').forEach(x => x.classList.toggle('on', x === b));
    document.getElementById('fp-player').innerHTML = `<iframe src="https://open.spotify.com/embed/track/${b.dataset.sp}?utm_source=generator&theme=0" title="${b.textContent}" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture" loading="lazy"></iframe>`;
  });
  chr.addEventListener('mouseover', e => { const n = e.target.closest('[data-b]'); if (n) showBand(n.dataset.b); });
  chr.addEventListener('keydown', e => { const n = e.target.closest('[data-b]'); if (n && (e.key === 'Enter' || e.key === ' ')) { e.preventDefault(); showBand(n.dataset.b); } });
  showBand('piano');
})();
</script>
{% endraw %}
