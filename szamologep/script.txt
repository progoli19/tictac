setTimeout(()=>{
    document.getElementById("szg").innerHTML = `<table>
    <tr><td colspan="5"><input id="input"></td></tr>
    ${["123*√","456/²","789-=","C0.+"].map((v,i) => `<tr>${v.split("").map((v,j) => 
        `<td id="x${i}-${j}" onclick="f(this.innerHTML)" ${i == 2 && j==4 ? "rowspan='2'" : ""}>${v}</td>`
    ).join("")}</tr>`).join("")}
    </table>`
}, 500)
function f(s) {
    if (s == '=') {
        document.getElementById("input").value = eval(document.getElementById("input").value)
    }
    else if(s == 'C') {
        document.getElementById("input").value = ""
    }
    else if(s == '²') {
        document.getElementById("input").value = Number(document.getElementById("input").value) ** 2
    }
    else if(s == '√') {
        document.getElementById("input").value = Math.sqrt(Number(document.getElementById("input").value))
    }
    else {
        document.getElementById("input").value += s
    }
}