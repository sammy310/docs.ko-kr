---
title: dotnet new에 대한 항목 템플릿 만들기 - .NET Core CLI
description: dotnet new 명령에 대한 항목 템플릿을 만드는 방법을 알아봅니다. 항목 템플릿에 포함할 수 있는 파일 수에는 제한이 없습니다.
author: thraka
ms.date: 06/25/2019
ms.topic: tutorial
ms.author: adegeo
ms.openlocfilehash: 5f4038e863d9bb59df470d3516c08fd2ad29c078
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503562"
---
# <a name="tutorial-create-an-item-template"></a><span data-ttu-id="0a088-104">자습서: 항목 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="0a088-104">Tutorial: Create an item template</span></span>

<span data-ttu-id="0a088-105">.NET Core를 사용하여 프로젝트, 파일, 리소스를 생성하는 템플릿을 만들고 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-105">With .NET Core, you can create and deploy templates that generate projects, files, even resources.</span></span> <span data-ttu-id="0a088-106">이 자습서는 `dotnet new` 명령에 사용할 템플릿을 만들고, 설치하고, 제거하는 방법을 알려주는 시리즈의 1부입니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-106">This tutorial is part one of a series that teaches you how to create, install, and uninstall, templates for use with the `dotnet new` command.</span></span>

<span data-ttu-id="0a088-107">시리즈의 1부에서는 다음 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-107">In this part of the series, you'll learn how to:</span></span>

> [!div class="checklist"]
>
> * <span data-ttu-id="0a088-108">항목 템플릿에 대한 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="0a088-108">Create a class for an item template</span></span>
> * <span data-ttu-id="0a088-109">템플릿 구성 폴더 및 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="0a088-109">Create the template config folder and file</span></span>
> * <span data-ttu-id="0a088-110">파일 경로에서 템플릿 설치</span><span class="sxs-lookup"><span data-stu-id="0a088-110">Install a template from a file path</span></span>
> * <span data-ttu-id="0a088-111">항목 템플릿 테스트</span><span class="sxs-lookup"><span data-stu-id="0a088-111">Test an item template</span></span>
> * <span data-ttu-id="0a088-112">항목 템플릿 제거</span><span class="sxs-lookup"><span data-stu-id="0a088-112">Uninstall an item template</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0a088-113">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0a088-113">Prerequisites</span></span>

* <span data-ttu-id="0a088-114">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download) 이상 버전</span><span class="sxs-lookup"><span data-stu-id="0a088-114">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download) or later versions.</span></span>
* <span data-ttu-id="0a088-115">참조 문서 [dotnet new에 대한 사용자 지정 템플릿](../tools/custom-templates.md)을 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="0a088-115">Read the reference article [Custom templates for dotnet new](../tools/custom-templates.md).</span></span>

  <span data-ttu-id="0a088-116">이 참조 문서에서는 템플릿에 대한 기본 사항과 템플릿을 취합하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-116">The reference article explains the basics about templates and how they're put together.</span></span> <span data-ttu-id="0a088-117">이 참조 문서의 정보 일부가 여기에도 나옵니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-117">Some of this information will be reiterated here.</span></span>

* <span data-ttu-id="0a088-118">터미널을 열고 _working\templates_ 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-118">Open a terminal and navigate to the _working\templates_ folder.</span></span>

## <a name="create-the-required-folders"></a><span data-ttu-id="0a088-119">필요한 폴더 만들기</span><span class="sxs-lookup"><span data-stu-id="0a088-119">Create the required folders</span></span>

<span data-ttu-id="0a088-120">이 시리즈에서는 템플릿 소스가 포함되는 “작업 폴더”와 템플릿을 테스트하는 데 사용되는 “테스트 폴더”를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-120">This series uses a "working folder" where your template source is contained and a "testing folder" used to test your templates.</span></span> <span data-ttu-id="0a088-121">작업 폴더와 테스트 폴더는 동일한 부모 폴더 아래에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-121">The working folder and testing folder should be under the same parent folder.</span></span>

<span data-ttu-id="0a088-122">먼저 부모 폴더를 만듭니다. 이름은 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-122">First, create the parent folder, the name does not matter.</span></span> <span data-ttu-id="0a088-123">그런 다음 _working_이라는 하위 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-123">Then, create a subfolder named _working_.</span></span> <span data-ttu-id="0a088-124">_working_ 폴더 내부에 _templates_이라는 하위 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-124">Inside of the _working_ folder, create a subfolder named _templates_.</span></span>

<span data-ttu-id="0a088-125">그런 다음 부모 폴더 아래에 _test_라는 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-125">Next, create a folder under the parent folder named _test_.</span></span> <span data-ttu-id="0a088-126">폴더 구조는 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-126">The folder structure should look like the following.</span></span>

```console
parent_folder
├───test
└───working
    └───templates
```

## <a name="create-an-item-template"></a><span data-ttu-id="0a088-127">항목 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="0a088-127">Create an item template</span></span>

<span data-ttu-id="0a088-128">항목 템플릿은 하나 이상의 파일을 포함하는 특정 형식의 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-128">An item template is a specific type of template that contains one or more files.</span></span> <span data-ttu-id="0a088-129">이러한 형식의 템플릿은 구성, 코드 또는 솔루션 파일과 같은 항목을 생성하려는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-129">These types of templates are useful when you want to generate something like a config, code, or solution file.</span></span> <span data-ttu-id="0a088-130">이 예제에서는 문자열 형식에 확장 메서드를 추가하는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-130">In this example, you'll create a class that adds an extension method to the string type.</span></span>

<span data-ttu-id="0a088-131">터미널에서 _working\templates_ 폴더로 이동하고 _extensions_라는 새 하위 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-131">In your terminal, navigate to the _working\templates_ folder and create a new subfolder named _extensions_.</span></span> <span data-ttu-id="0a088-132">폴더로 들어갑니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-132">Enter the folder.</span></span>

```console
working
└───templates
    └───extensions
```

<span data-ttu-id="0a088-133">_CommonExtensions.cs_라는 새 파일을 만들고 원하는 텍스트 편집기를 사용하여 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-133">Create a new file named _CommonExtensions.cs_ and open it with your favorite text editor.</span></span> <span data-ttu-id="0a088-134">이 클래스는 문자열의 내용을 반전하는 `Reverse`라는 확장 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-134">This class will provide an extension method named `Reverse` that reverses the contents of a string.</span></span> <span data-ttu-id="0a088-135">다음 코드를 붙여넣고 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-135">Paste in the following code and save the file:</span></span>

```csharp
using System;

namespace System
{
    public static class StringExtensions
    {
        public static string Reverse(this string value)
        {
            var tempArray = value.ToCharArray();
            Array.Reverse(tempArray);
            return new string(tempArray);
        }
    }
}
```

<span data-ttu-id="0a088-136">템플릿의 콘텐츠를 만들었으므로 이제 템플릿의 루트 폴더에 템플릿 구성을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-136">Now that you have the content of the template created, you need to create the template config at the root folder of the template.</span></span>

## <a name="create-the-template-config"></a><span data-ttu-id="0a088-137">템플릿 구성 만들기</span><span class="sxs-lookup"><span data-stu-id="0a088-137">Create the template config</span></span>

<span data-ttu-id="0a088-138">템플릿은 .NET Core의 템플릿 루트에 있는 특수 폴더 및 구성 파일에서 인식됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-138">Templates are recognized in .NET Core by a special folder and config file that exist at the root of your template.</span></span> <span data-ttu-id="0a088-139">이 자습서에서 템플릿 폴더는 _working\templates\extensions_에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-139">In this tutorial, your template folder is located at _working\templates\extensions_.</span></span>

<span data-ttu-id="0a088-140">템플릿을 만들 때 템플릿 폴더의 모든 파일과 폴더는 특수 구성 폴더를 제외하고 템플릿의 일부로 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-140">When you create a template, all files and folders in the template folder are included as part of the template except for the special config folder.</span></span> <span data-ttu-id="0a088-141">이 구성 폴더는 _.template.config_입니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-141">This config folder is named _.template.config_.</span></span>

<span data-ttu-id="0a088-142">먼저 _.template.config_라는 새 하위 폴더를 만들고 폴더로 들어갑니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-142">First, create a new subfolder named _.template.config_, enter it.</span></span> <span data-ttu-id="0a088-143">그런 다음 _template.json_이라는 새 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-143">Then, create a new file named _template.json_.</span></span> <span data-ttu-id="0a088-144">폴더 구조는 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-144">Your folder structure should look like this:</span></span>

```console
working
└───templates
    └───extensions
        └───.template.config
                template.json
```

<span data-ttu-id="0a088-145">원하는 텍스트 편집기에서 _template.json_을 열고 다음 JSON 코드를 붙여넣고 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-145">Open the _template.json_ with your favorite text editor and paste in the following JSON code and save it.</span></span>

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Me",
  "classifications": [ "Common", "Code" ],
  "identity": "ExampleTemplate.StringExtensions",
  "name": "Example templates: string extensions",
  "shortName": "stringext",
  "tags": {
    "language": "C#",
    "type": "item"
  }
}
```

<span data-ttu-id="0a088-146">이 구성 파일에는 템플릿에 대한 모든 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-146">This config file contains all the settings for your template.</span></span> <span data-ttu-id="0a088-147">기본 설정(예: `name` 및 `shortName`)도 확인할 수 있지만 `item`으로 설정된 `tags/type` 값도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-147">You can see the basic settings, such as `name` and `shortName`, but there's also a `tags/type` value that is set to `item`.</span></span> <span data-ttu-id="0a088-148">이 값에 따라, 만든 템플릿이 항목 템플릿으로 분류됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-148">This categorizes your template as an item template.</span></span> <span data-ttu-id="0a088-149">만드는 템플릿 형식에 대한 제한은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-149">There's no restriction on the type of template you create.</span></span> <span data-ttu-id="0a088-150">`item` 및 `project` 값은 사용자가 검색 중인 템플릿 형식을 쉽게 필터링할 수 있도록 .NET Core에서 권장하는 일반적인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-150">The `item` and `project` values are common names that .NET Core recommends so that users can easily filter the type of template they're searching for.</span></span>

<span data-ttu-id="0a088-151">`classifications` 항목은 `dotnet new`를 실행할 때 표시되고 템플릿 목록을 가져오는 **태그** 열을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-151">The `classifications` item represents the **tags** column you see when you run `dotnet new` and get a list of templates.</span></span> <span data-ttu-id="0a088-152">사용자는 분류 태그를 기준으로 검색할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-152">Users can also search based on classification tags.</span></span> <span data-ttu-id="0a088-153">\*.json 파일의 `tags` 속성을 `classifications` 태그 목록과 혼동하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="0a088-153">Don't confuse the `tags` property in the \*.json file with the `classifications` tags list.</span></span> <span data-ttu-id="0a088-154">불행히도 두 항목은 이름이 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-154">They're two different things unfortunately named similarly.</span></span> <span data-ttu-id="0a088-155">*template.json* 파일에 대한 전체 스키마는 [JSON Schema Store](http://json.schemastore.org/template)(JSON 스키마 저장소)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-155">The full schema for the *template.json* file is found at the [JSON Schema Store](http://json.schemastore.org/template).</span></span> <span data-ttu-id="0a088-156">*template.json* 파일에 대한 자세한 내용은 [dotnet 템플릿 wiki](https://github.com/dotnet/templating/wiki)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0a088-156">For more information about the *template.json* file, see the [dotnet templating wiki](https://github.com/dotnet/templating/wiki).</span></span>

<span data-ttu-id="0a088-157">유효한 _.template.config/template.json_ 파일이 있으므로 이제 템플릿을 설치할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-157">Now that you have a valid _.template.config/template.json_ file, your template is ready to be installed.</span></span> <span data-ttu-id="0a088-158">터미널에서 _extensions_ 폴더로 이동하고 다음 명령을 실행하여 현재 폴더에 있는 템플릿을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-158">In your terminal, navigate to the  _extensions_ folder and run the following command to install the template located at the current folder:</span></span>

* <span data-ttu-id="0a088-159">**Windows**: `dotnet new -i .\`</span><span class="sxs-lookup"><span data-stu-id="0a088-159">**On Windows**: `dotnet new -i .\`</span></span>
* <span data-ttu-id="0a088-160">**Linux 또는 macOS**: `dotnet new -i ./`</span><span class="sxs-lookup"><span data-stu-id="0a088-160">**On Linux or macOS**: `dotnet new -i ./`</span></span>

<span data-ttu-id="0a088-161">이 명령은 사용자 템플릿을 포함하여 설치된 템플릿 목록을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-161">This command outputs the list of templates installed, which should include yours.</span></span>

```console
C:\working\templates\extensions> dotnet new -i .\
Usage: new [options]

Options:
  -h, --help          Displays help for this command.
  -l, --list          Lists templates containing the specified name. If no name is specified, lists all templates.

... cut to save space ...

Templates                                         Short Name            Language          Tags
-------------------------------------------------------------------------------------------------------------------------------
Example templates: string extensions              stringext             [C#]              Common/Code
Console Application                               console               [C#], F#, VB      Common/Console
Class library                                     classlib              [C#], F#, VB      Common/Library
WPF Application                                   wpf                   [C#], VB          Common/WPF
Windows Forms (WinForms) Application              winforms              [C#], VB          Common/WinForms
Worker Service                                    worker                [C#]              Common/Worker/Web
```

## <a name="test-the-item-template"></a><span data-ttu-id="0a088-162">항목 템플릿 테스트</span><span class="sxs-lookup"><span data-stu-id="0a088-162">Test the item template</span></span>

<span data-ttu-id="0a088-163">항목 템플릿을 설치했으므로 이제 템플릿을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-163">Now that you have an item template installed, test it.</span></span> <span data-ttu-id="0a088-164">_test/_ 폴더로 이동하고 `dotnet new console`을 사용하여 새 콘솔 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-164">Navigate to the _test/_ folder and create a new console application with `dotnet new console`.</span></span> <span data-ttu-id="0a088-165">그러면 `dotnet run` 명령으로 쉽게 테스트할 수 있는 작업 프로젝트가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-165">This generates a working project you can easily test with the `dotnet run` command.</span></span>

```dotnetcli
dotnet new console
```

<span data-ttu-id="0a088-166">그러면 다음과 같은 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-166">You get output similar to the following.</span></span>

```console
The template "Console Application" was created successfully.

Processing post-creation actions...
Running 'dotnet restore' on C:\test\test.csproj...
  Restore completed in 54.82 ms for C:\test\test.csproj.

Restore succeeded.
```

<span data-ttu-id="0a088-167">프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-167">Run the project with.</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="0a088-168">다음과 같은 출력을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-168">You get the following output.</span></span>

```console
Hello World!
```

<span data-ttu-id="0a088-169">이제 `dotnet new stringext`를 실행하여 템플릿에서 _CommonExtensions.cs_를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-169">Next, run `dotnet new stringext` to generate the _CommonExtensions.cs_ from the template.</span></span>

```dotnetcli
dotnet new stringext
```

<span data-ttu-id="0a088-170">다음과 같은 출력을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-170">You get the following output.</span></span>

```console
The template "Example templates: string extensions" was created successfully.
```

<span data-ttu-id="0a088-171">템플릿에 제공된 확장 메서드를 사용하여 `"Hello World"` 문자열을 반전하도록 _Program.cs_에서 코드를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-171">Change the code in _Program.cs_ to reverse the `"Hello World"` string with the extension method provided by the template.</span></span>

```csharp
Console.WriteLine("Hello World!".Reverse());
```

<span data-ttu-id="0a088-172">프로그램을 다시 실행하면 결과가 반전된 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-172">Run the program again and you'll see that the result is reversed.</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="0a088-173">다음과 같은 출력을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-173">You get the following output.</span></span>

```console
!dlroW olleH
```

<span data-ttu-id="0a088-174">지금까지</span><span class="sxs-lookup"><span data-stu-id="0a088-174">Congratulations!</span></span> <span data-ttu-id="0a088-175">.NET Core를 사용하여 항목 템플릿을 만들고 배포했습니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-175">You created and deployed an item template with .NET Core.</span></span> <span data-ttu-id="0a088-176">이 자습서 시리즈의 다음 부분에 대비하여, 여기서 만든 템플릿을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-176">In preparation for the next part of this tutorial series, you must uninstall the template you created.</span></span> <span data-ttu-id="0a088-177">또한 _test_ 폴더에서 모든 파일을 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-177">Make sure to delete all files from the _test_ folder too.</span></span> <span data-ttu-id="0a088-178">그러면 이 자습서의 다음 주요 섹션을 위해 정리된 상태로 되돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-178">This will get you back to a clean state ready for the next major section of this tutorial.</span></span>

## <a name="uninstall-the-template"></a><span data-ttu-id="0a088-179">템플릿 제거</span><span class="sxs-lookup"><span data-stu-id="0a088-179">Uninstall the template</span></span>

<span data-ttu-id="0a088-180">파일 경로를 사용하여 템플릿을 설치했으므로 **절대** 파일 경로를 사용하여 템플릿을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-180">Because you installed the template by file path, you must uninstall it with the **absolute** file path.</span></span> <span data-ttu-id="0a088-181">`dotnet new -u` 명령을 실행하여 설치된 템플릿 목록을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-181">You can see a list of templates installed by running the `dotnet new -u` command.</span></span> <span data-ttu-id="0a088-182">사용자 템플릿은 마지막에 나열되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-182">Your template should be listed last.</span></span> <span data-ttu-id="0a088-183">`dotnet new -u <ABSOLUTE PATH TO TEMPLATE DIRECTORY>` 명령을 사용하여 템플릿을 제거하려면 나열된 경로를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-183">Use the path listed to uninstall your template with the `dotnet new -u <ABSOLUTE PATH TO TEMPLATE DIRECTORY>` command.</span></span>

```dotnetcli
dotnet new -u
```

<span data-ttu-id="0a088-184">그러면 다음과 같은 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-184">You get output similar to the following.</span></span>

```console
Template Instantiation Commands for .NET Core CLI

Currently installed items:
  Microsoft.DotNet.Common.ItemTemplates
    Templates:
      dotnet gitignore file (gitignore)
      global.json file (globaljson)
      NuGet Config (nugetconfig)
      Solution File (sln)
      Dotnet local tool manifest file (tool-manifest)
      Web Config (webconfig)

... cut to save space ...

  NUnit3.DotNetNew.Template
    Templates:
      NUnit 3 Test Project (nunit) C#
      NUnit 3 Test Item (nunit-test) C#
      NUnit 3 Test Project (nunit) F#
      NUnit 3 Test Item (nunit-test) F#
      NUnit 3 Test Project (nunit) VB
      NUnit 3 Test Item (nunit-test) VB
  C:\working\templates\extensions
    Templates:
      Example templates: string extensions (stringext) C#
```

<span data-ttu-id="0a088-185">템플릿을 제거하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-185">To uninstall a template, run the following command.</span></span>

```dotnetcli
dotnet new -u C:\working\templates\extensions
```

## <a name="next-steps"></a><span data-ttu-id="0a088-186">다음 단계</span><span class="sxs-lookup"><span data-stu-id="0a088-186">Next steps</span></span>

<span data-ttu-id="0a088-187">이 자습서에서는 항목 템플릿을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="0a088-187">In this tutorial, you created an item template.</span></span> <span data-ttu-id="0a088-188">프로젝트 템플릿을 만드는 방법을 알아보려면 이 자습서 시리즈를 계속 진행하세요.</span><span class="sxs-lookup"><span data-stu-id="0a088-188">To learn how to create a project template, continue this tutorial series.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="0a088-189">프로젝트 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="0a088-189">Create a project template</span></span>](cli-templates-create-project-template.md)
