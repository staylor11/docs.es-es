---
title: Habilitación de la finalización con tabulación
description: En este artículo se describe cómo habilitar la finalización con tabulación para la CLI de .NET Core para PowerShell, Bash y zsh.
author: thraka
ms.author: adegeo
ms.date: 12/17/2018
ms.openlocfilehash: 10b2e13aad9821295efc5c36d1cad04f1a95477c
ms.sourcegitcommit: 0888d7b24f475c346a3f444de8d83ec1ca7cd234
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2018
ms.locfileid: "53784401"
---
# <a name="how-to-enable-tab-completion-for-the-net-core-cli"></a><span data-ttu-id="630c5-103">Cómo habilitar la finalización con tabulación para la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="630c5-103">How to enable TAB completion for the .NET Core CLI</span></span>

<span data-ttu-id="630c5-104">A partir del SDK de .NET Core 2.0, la CLI de .NET Core admite la finalización con tabulación.</span><span class="sxs-lookup"><span data-stu-id="630c5-104">Starting with .NET Core 2.0 SDK, the .NET Core CLI supports tab completion.</span></span> <span data-ttu-id="630c5-105">En este artículo se describe cómo configurar la finalización con tabulación para tres shells: PowerShell, Bash y zsh.</span><span class="sxs-lookup"><span data-stu-id="630c5-105">This article describes how to configure tab completion for three shells, PowerShell, Bash, and zsh.</span></span> <span data-ttu-id="630c5-106">Otros shells pueden tener compatibilidad con la finalización automática.</span><span class="sxs-lookup"><span data-stu-id="630c5-106">Other shells may have support for auto completion.</span></span> <span data-ttu-id="630c5-107">Consulte su documentación sobre cómo configurar la finalización automática, los pasos deben ser similares a los que se describen en este artículo.</span><span class="sxs-lookup"><span data-stu-id="630c5-107">Refer to their documentation on how to configure auto completion, the steps should be similar to the steps described in this article.</span></span>

[!INCLUDE [topic-appliesto-net-core-2plus](~/includes/topic-appliesto-net-core-2plus.md)]

<span data-ttu-id="630c5-108">Una vez configurada, para desencadenar la finalización con tabulación para la CLI de .NET Core, escriba un comando `dotnet ` en el shell y, después, presione el tabulador.</span><span class="sxs-lookup"><span data-stu-id="630c5-108">Once setup, tab completion for the .NET Core CLI is triggered by typing a `dotnet ` command in the shell, and then hitting the TAB key.</span></span> <span data-ttu-id="630c5-109">La línea de comandos que se envía al comando `dotnet complete` y los resultados se procesan mediante el shell.</span><span class="sxs-lookup"><span data-stu-id="630c5-109">The current command line is sent to the `dotnet complete` command, and the results are processed by your shell.</span></span> <span data-ttu-id="630c5-110">Puede probar los resultados sin habilitar la finalización con tabulación si envía algo directamente al comando `dotnet complete`.</span><span class="sxs-lookup"><span data-stu-id="630c5-110">You can test the results without enabling tab completion by sending something directly to the `dotnet complete` command.</span></span> <span data-ttu-id="630c5-111">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="630c5-111">For example:</span></span>

```
> dotnet complete "dotnet a"
add
clean
--diagnostics
migrate
pack
```

<span data-ttu-id="630c5-112">Si ese comando no funciona, asegúrese de que está instalado el SDK de .NET Core 2.0 o una versión superior.</span><span class="sxs-lookup"><span data-stu-id="630c5-112">If that command doesn't work, make sure that .NET Core 2.0 SDK or above is installed.</span></span> <span data-ttu-id="630c5-113">Si está instalado pero ese comando sigue sin funcionar, asegúrese de que el comando `dotnet` se resuelve en una versión de .NET Core 2.0 y posteriores.</span><span class="sxs-lookup"><span data-stu-id="630c5-113">If it's installed, but that command still doesn't work, make sure that the `dotnet` command resolves to a version of .NET Core 2.0 and above.</span></span> <span data-ttu-id="630c5-114">Use el comando `dotnet --version` para ver en qué versión de `dotnet` se resuelve la ruta de acceso actual.</span><span class="sxs-lookup"><span data-stu-id="630c5-114">Use the `dotnet --version` command to see what version of `dotnet` your current path is resolving to.</span></span> <span data-ttu-id="630c5-115">Para obtener más información, vea [Selección de la versión de .NET Core que se va a usar](../versions/selection.md).</span><span class="sxs-lookup"><span data-stu-id="630c5-115">For more information, see [Select the .NET Core version to use](../versions/selection.md).</span></span>

### <a name="examples"></a><span data-ttu-id="630c5-116">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="630c5-116">Examples</span></span>

<span data-ttu-id="630c5-117">Estos son algunos ejemplos de lo que proporciona la finalización con tabulación:</span><span class="sxs-lookup"><span data-stu-id="630c5-117">Here are some examples of what tab completion provides:</span></span>

<span data-ttu-id="630c5-118">Entrada</span><span class="sxs-lookup"><span data-stu-id="630c5-118">Input</span></span>                                | <span data-ttu-id="630c5-119">se convierte en</span><span class="sxs-lookup"><span data-stu-id="630c5-119">becomes</span></span>                                                                     | <span data-ttu-id="630c5-120">porque</span><span class="sxs-lookup"><span data-stu-id="630c5-120">because</span></span>
:------------------------------------|:----------------------------------------------------------------------------|:--------------------------------
`dotnet a⇥`                          | `dotnet add`                                                                 | <span data-ttu-id="630c5-121">`add` es el primer subcomando, por orden alfabético.</span><span class="sxs-lookup"><span data-stu-id="630c5-121">`add` is the first subcommand, alphabetically.</span></span>
`dotnet add p⇥`                      | `dotnet add --help`                                                          | <span data-ttu-id="630c5-122">La finalización con tabulación hace coincidir las subcadenas y `--help` aparece primero alfabéticamente.</span><span class="sxs-lookup"><span data-stu-id="630c5-122">Tab completion matches substrings and `--help` comes first alphabetically.</span></span>
`dotnet add p⇥⇥`                    | `dotnet add package`                                                          | <span data-ttu-id="630c5-123">Al presionar la tecla Tab una segunda vez aparece la siguiente sugerencia.</span><span class="sxs-lookup"><span data-stu-id="630c5-123">Pressing tab a second time brings up the next suggestion.</span></span>      
`dotnet add package Microsoft⇥`      | `dotnet add package Microsoft.ApplicationInsights.Web`                      | <span data-ttu-id="630c5-124">Los resultados se devuelven por orden alfabético.</span><span class="sxs-lookup"><span data-stu-id="630c5-124">Results are returned alphabetically.</span></span>
`dotnet remove reference ⇥`          | `dotnet remove reference ..\..\src\OmniSharp.DotNet\OmniSharp.DotNet.csproj` | <span data-ttu-id="630c5-125">La finalización con tabulación es compatible con archivos de proyecto.</span><span class="sxs-lookup"><span data-stu-id="630c5-125">Tab completion is project file aware.</span></span>

## <a name="powershell"></a><span data-ttu-id="630c5-126">PowerShell</span><span class="sxs-lookup"><span data-stu-id="630c5-126">PowerShell</span></span>

<span data-ttu-id="630c5-127">Para agregar finalización con tabulación a **PowerShell** para la CLI de .NET Core, cree o edite el perfil almacenado en la variable `$PROFILE`.</span><span class="sxs-lookup"><span data-stu-id="630c5-127">To add tab completion to **PowerShell** for the .NET Core CLI, create or edit the profile stored in the variable `$PROFILE`.</span></span> <span data-ttu-id="630c5-128">Para obtener más información, vea [Cómo crear el perfil](/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-6#how-to-create-a-profile) y [Los perfiles y la directiva de ejecución](/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-6#profiles-and-execution-policy).</span><span class="sxs-lookup"><span data-stu-id="630c5-128">For more information, see [How to create your profile](/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-6#how-to-create-a-profile) and [Profiles and execution policy](/powershell/module/microsoft.powershell.core/about/about_profiles?view=powershell-6#profiles-and-execution-policy).</span></span> 

<span data-ttu-id="630c5-129">Agregue el código siguiente al perfil:</span><span class="sxs-lookup"><span data-stu-id="630c5-129">Add the following code to your profile:</span></span>

```powershell
# PowerShell parameter completion shim for the dotnet CLI 
Register-ArgumentCompleter -Native -CommandName dotnet -ScriptBlock {
     param($commandName, $wordToComplete, $cursorPosition)
         dotnet complete --position $cursorPosition "$wordToComplete" | ForEach-Object {
            [System.Management.Automation.CompletionResult]::new($_, $_, 'ParameterValue', $_)
         }
 }
```

## <a name="bash"></a><span data-ttu-id="630c5-130">Bash</span><span class="sxs-lookup"><span data-stu-id="630c5-130">Bash</span></span>

<span data-ttu-id="630c5-131">Para agregar finalización con tabulación al shell de **bash** para la CLI de .NET Core, agregue el código siguiente al archivo `.bashrc`:</span><span class="sxs-lookup"><span data-stu-id="630c5-131">To add tab completion to your **bash** shell for the .NET Core CLI, add the following code to your `.bashrc` file:</span></span>

```bash
# bash parameter completion for the dotnet CLI

_dotnet_bash_complete()
{
  local word=${COMP_WORDS[COMP_CWORD]}

  local completions
  completions="$(dotnet complete --position "${COMP_POINT}" "${COMP_LINE}")"

  COMPREPLY=( $(compgen -W "$completions" -- "$word") )
}

complete -f -F _dotnet_bash_complete dotnet
```

## <a name="zsh"></a><span data-ttu-id="630c5-132">Zsh</span><span class="sxs-lookup"><span data-stu-id="630c5-132">Zsh</span></span>

<span data-ttu-id="630c5-133">Para agregar finalización con tabulación al shell de **zsh** para la CLI de .NET Core, agregue el código siguiente al archivo `.zshrc`:</span><span class="sxs-lookup"><span data-stu-id="630c5-133">To add tab completion to your **zsh** shell for the .NET Core CLI, add the following code to your `.zshrc` file:</span></span>

```zsh
# zsh parameter completion for the dotnet CLI

_dotnet_zsh_complete() 
{
  local completions=("$(dotnet complete "$words")")

  reply=( "${(ps:\n:)completions}" )
}

compctl -K _dotnet_zsh_complete dotnet
```