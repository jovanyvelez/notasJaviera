<script lang="ts">
  import { createHighlighter } from 'shiki';




  (async () => {

    const highlighter = await createHighlighter({
      themes: ['catppuccin-mocha'],
      langs: ['csharp'],
    })


    const html = highlighter.codeToHtml(`
  using System;

    namespace MiPrimerPrograma
    {
        class Program
        {
            static void Main(string[] args)
            {
                Console.WriteLine("¡Hola Mundo!");
                Console.ReadLine(); // Espera a que el usuario presione Enter
            }
        }
    }

` , { lang: 'csharp', theme: 'catppuccin-mocha' });

    return html

  })();



</script>

{@html html}
