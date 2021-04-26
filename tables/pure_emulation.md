---
layout: default
---


## Pure Emulation
<table>
  <colgroup span="4"></colgroup>
  <colgroup span="3"></colgroup>
  <colgroup span="2"></colgroup>
  <tr>
  </tr>

  <tr>
    <th colspan="1" scope="colgroup"></th>
    <th colspan="4" scope="colgroup">Layer</th>
    <th colspan="3" scope="colgroup">Target</th>
    <th colspan="2" scope="colgroup">Availability<sup>*</sup></th>
  </tr>
  <tr>
    <th scope="col">System</th>
    <th scope="col">Hardware</th>
    <th scope="col">OS</th>
    <th scope="col">Application</th>
    <th scope="col">Function</th>
    <th scope="col">Type<sup>†</sup></th>
    <th scope="col">ISA(s)</th>
    <th scope="col">Binary?</th>
    <th scope="col">Source code</th>
    <th scope="col">Data Set</th>
  </tr>

    {% assign sorted = site.data | sort %}
    {% for systems in sorted %}
        {% for system in systems %}
            {% if system.category != "pure_emulation" %}
             {% continue %}
            {% endif %}

    <tr>
    <td> <a href="{{ system.urls.paper }}" >{{ system.name }} </a> </td>
    <td>
        {% if system.hardware.passthrough == true %}
            <img src="pass.png" alt="passthrough">
        {% else %}
            <img src="none.png">
        {% endif %}
        {% if system.hardware.emulated == true %}
            <img src="emul.png" alt="emulated">
        {% else %}
            <img src="none.png">
        {% endif %}
        {% if system.hardware.replaced == true %}
            <img src="repl.png" alt="repl">
        {% else %}
            <img src="none.png">
        {% endif %}
        {% if system.hardware.symbolic == true %}
            <img src="symb.png" alt="symbolic">
        {% else %}
            <img src="none.png">
        {% endif %}
     </td>

    <td>

        {% if system.os %}
            {% if system.os.passthrough == true %}
                <img src="pass.png" alt="passthrough">
            {% else %}
                <img src="none.png">
            {% endif %}
            {% if system.os.emulated == true %}
                <img src="emul.png" alt="emulated">
            {% else %}
                <img src="none.png">
            {% endif %}
            {% if system.os.unmodified == true %}
                <img src="unmd.png" alt="unmodified">
            {% else %}
                <img src="none.png">
            {% endif %}
            {% if system.os.replaced == true %}
                <img src="repl.png" alt="repl">
            {% else %}
                <img src="none.png">
            {% endif %}
            {% if system.os.symbolic == true %}
                <img src="symb.png" alt="symbolic">
            {% else %}
                <img src="none.png">
            {% endif %}
        {% else %}
            —
        {% endif %}

     </td>

    <td>
        {% if system.application.passthrough == true %}
            <img src="pass.png" alt="passthrough">
        {% else %}
            <img src="none.png">
        {% endif %}
        {% if system.application.emulated == true %}
            <img src="emul.png" alt="emulated">
        {% else %}
            <img src="none.png">
        {% endif %}
        {% if system.application.unmodified == true %}
            <img src="unmd.png" alt="unmodified">
        {% else %}
            <img src="none.png">
        {% endif %}
        {% if system.application.replaced == true %}
            <img src="repl.png" alt="repl">
        {% else %}
            <img src="none.png">
        {% endif %}
        {% if system.application.symbolic == true %}
            <img src="symb.png" alt="symbolic">
        {% else %}
            <img src="none.png">
        {% endif %}
     </td>

    <td>
        {% if system.function.passthrough == true %}
            <img src="pass.png" alt="passthrough">
        {% else %}
            <img src="none.png">
        {% endif %}
        {% if system.function.emulated == true %}
            <img src="emul.png" alt="emulated">
        {% else %}
            <img src="none.png">
        {% endif %}
        {% if system.function.unmodified == true %}
            <img src="unmd.png" alt="unmodified">
        {% else %}
            <img src="none.png">
        {% endif %}
        {% if system.function.replaced == true %}
            <img src="repl.png" alt="repl">
        {% else %}
            <img src="none.png">
        {% endif %}
        {% if system.function.symbolic == true %}
            <img src="symb.png" alt="symbolic">
        {% else %}
            <img src="none.png">
        {% endif %}
     </td>

    <td> {{ system.target.type }} </td>
    <td> {{ system.target.isas }} </td>
    <td> {% if system.target.binary == true %} ✔️ {% endif %} </td>
    <td>
       {% if system.availability.source == true %}  <a href="{{ system.urls.source }}" > ✔️ </a>
       {% elsif system.availability.source == "partial" %}  <a href="{{ system.urls.source }}" > ~ </a>
       {% endif %}
    </td>
    <td>
       {% if system.availability.data_set == true %}  <a href="{{ system.urls.data_set }}" > ✔️ </a>
       {% elsif system.availability.data_set == "partial" %}  <a href="{{ system.urls.data_set }}" > ~ </a>
       {% endif %}
    </td>
    </tr>
        {% endfor %}
    {% endfor %}

</table>

&nbsp; Legend:
&nbsp; ![passthrough](pass.png): Passed through
&nbsp; ![emulated](emul.png): Emulated
&nbsp; ![unmodified](unmd.png): Not modified
&nbsp; ![replaced](repl.png): Replaced
&nbsp; ![symbolic](symb.png): Symbolic model
&nbsp; ~: Partial Availability

<sup>*</sup> When available, source code and data sets can be found by clicking on the checkmarks. <br/>
<sup>†</sup> Target types are described in our [faq]({{ site.baseurl }}{% link faq.md %}).
