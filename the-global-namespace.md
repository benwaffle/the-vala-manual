<div id="the-global-namespace" class="section level1">

The global namespace
====================

Everything not declared within a particular namespace declaration is
automatically in the global namespace. All defined namespaces are nested
inside the global namespace at some depth. This is also where the
fundamental types are defined.

If there is ever a need to explictly refer to an identifier in the
global namespace, the identifier can be prefixed with `global::` . This
will allow you, for example, to refer to a namespace which has the same
name as a local variable.

</div>
