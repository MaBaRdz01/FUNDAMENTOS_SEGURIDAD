## RETO
MatchTheRegex
## DESCRIPCION
How about trying to match a regular expression

Additional details will be available after launching your challenge instance.
## SOLUCION
Mirando el código fuente, encontramos:

f	function send_request() {
		let val = document.getElementById("name").value;
		// ^p.....F!?
		fetch(`/flag?input=${val}`)
			.then(res => res.text())
			.then(res => {
				const res_json = JSON.parse(res);
				alert(res_json.flag)
				return false;
			})
		return false;
	}

Aquí EN EL CODIGO  se puede ver claramente una pista:
// ^p.....F!?

**picoCTF{succ3ssfully_matchtheregex_0694f25b}**
## NOTAS ADICIONALES
`^`Indica el inicio de la cadena.
`$`Indica el final de la cadena.
`.`Cualquier carácter (letra, número, símbolo).
`*`Cero o más repeticiones del carácter anterior.
`+`Una o más repeticiones del carácter anterior.

## REFERENCIAS
https://regexr.com/