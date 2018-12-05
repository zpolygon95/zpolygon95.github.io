---
layout: page
title: Projects
---

<script>
function httpGetAsync(theUrl, callback)
{
    var xmlHttp = new XMLHttpRequest();
    xmlHttp.onreadystatechange = function() {
        if (xmlHttp.readyState == 4 && xmlHttp.status == 200)
            callback(xmlHttp.responseText);
    }
    xmlHttp.open("GET", theUrl, true);
    xmlHttp.send(null);
}
url = "https://docs.google.com/spreadsheets/d/e/2PACX-1vSW89akFGUgrUjepjdT70ni6RCRhg0pfp6-r_oCRTssGM4yiPH5bz9C5InJwfORbENiKxwKGg8hRlIP/pub?output=csv";
httpGetAsync(url, function (text) {
    lines = text.split("\n");
    out = "";
    for (i in lines)
    {
        rtag = (i == 0) ? "thead" : "tr";
        ctag = (i == 0) ? "th" : "td";
        out += "<" + rtag + ">";
        items = lines[i].split(",");
        for (j in items)
        {
            if (items[j].startsWith("http"))
                item = "<a href=\"" + items[j] + "\">link</a>";
            else
                item = items[j];
            out += "<" + ctag + ">" + item + "</" + ctag + ">";
        }
        out += "</" + rtag + ">";
    }
    table = document.getElementById("projects-table");
    table.innerHTML = out;
});
</script>

<table id="projects-table"></table>

See [my github account](https://github.com/zpolygon95) for source code!

[1]: https://github.com/zpolygon95/ctf_writeups
[2]: https://github.com/zpolygon95/language-cpu12
