---
title: 대화형 옵션
description: F# 대화형 fsi.exe에서 지 원하는 명령줄 옵션에 대해 알아봅니다.
ms.date: 08/15/2020
ms.openlocfilehash: adc8dc86f14366720e1acbf35115d4e318a76aef
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88810535"
---
# <a name="f-interactive-options"></a><span data-ttu-id="d30ff-103">F# 대화형 옵션</span><span class="sxs-lookup"><span data-stu-id="d30ff-103">F# Interactive options</span></span>

<span data-ttu-id="d30ff-104">이 문서에서는 F# 대화형에서 지 원하는 명령줄 옵션을 설명 합니다 `fsi.exe` .</span><span class="sxs-lookup"><span data-stu-id="d30ff-104">This article describes the command-line options supported by F# Interactive, `fsi.exe`.</span></span> <span data-ttu-id="d30ff-105">F# 대화형은 F # 컴파일러와 동일한 명령줄 옵션을 여러 개 사용할 수 있지만 몇 가지 추가 옵션도 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-105">F# Interactive accepts many of the same command-line options as the F# compiler, but also accepts some additional options.</span></span>

## <a name="use-f-interactive-for-scripting"></a><span data-ttu-id="d30ff-106">스크립팅에 F# 대화형 사용</span><span class="sxs-lookup"><span data-stu-id="d30ff-106">Use F# Interactive for scripting</span></span>

<span data-ttu-id="d30ff-107">F# 대화형는 `dotnet fsi` 대화형으로 실행 하거나 명령줄에서 실행 하 여 스크립트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-107">F# Interactive, `dotnet fsi`, can be launched interactively, or it can be launched from the command line to run a script.</span></span> <span data-ttu-id="d30ff-108">명령줄 구문은</span><span class="sxs-lookup"><span data-stu-id="d30ff-108">The command-line syntax is</span></span>

```dotnetcli
dotnet fsi [options] [ script-file [arguments] ]
```

<span data-ttu-id="d30ff-109">F # 스크립트 파일의 파일 확장명은 `.fsx` 입니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-109">The file extension for F# script files is `.fsx`.</span></span>

## <a name="table-of-f-interactive-options"></a><span data-ttu-id="d30ff-110">F# 대화형 옵션 표</span><span class="sxs-lookup"><span data-stu-id="d30ff-110">Table of F# Interactive Options</span></span>

<span data-ttu-id="d30ff-111">다음 표에서는 F# 대화형에서 지 원하는 옵션을 요약 하 여 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-111">The following table summarizes the options supported by F# Interactive.</span></span> <span data-ttu-id="d30ff-112">이러한 옵션은 명령줄 또는 Visual Studio IDE를 통해 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-112">You can set these options on the command line or through the Visual Studio IDE.</span></span> <span data-ttu-id="d30ff-113">Visual Studio IDE에서 이러한 옵션을 설정 하려면 **도구** 메뉴를 열고 **옵션**을 선택한 다음 **F # 도구** 노드를 확장 하 고 **F# 대화형**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-113">To set these options in the Visual Studio IDE, open the **Tools** menu, select **Options**, expand the **F# Tools** node, and then select **F# Interactive**.</span></span>

<span data-ttu-id="d30ff-114">목록 요소가 F# 대화형 옵션 인수에 표시 되는 경우 목록 요소는 세미콜론 ()으로 구분 됩니다 `;` .</span><span class="sxs-lookup"><span data-stu-id="d30ff-114">Where lists appear in F# Interactive option arguments, list elements are separated by semicolons (`;`).</span></span>

|<span data-ttu-id="d30ff-115">옵션</span><span class="sxs-lookup"><span data-stu-id="d30ff-115">Option</span></span>|<span data-ttu-id="d30ff-116">Description</span><span class="sxs-lookup"><span data-stu-id="d30ff-116">Description</span></span>|
|------|-----------|
|**--**|<span data-ttu-id="d30ff-117">**Fsi.exe my.application.commandlineargs**를 사용 하 여 코드에서 액세스할 수 있는 F # 프로그램 또는 스크립트에 대 한 명령줄 인수로 나머지 인수를 처리 하도록 F# 대화형에 지시 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-117">Used to instruct F# Interactive to treat remaining arguments as command-line arguments to the F# program or script, which you can access in code by using the list **fsi.CommandLineArgs**.</span></span>|
|<span data-ttu-id="d30ff-118">**--확인**됨 [ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="d30ff-118">**--checked**[**+**&#124;**-**]</span></span>|<span data-ttu-id="d30ff-119">**fsc.exe** 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-119">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="d30ff-120">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d30ff-120">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="d30ff-121">**--codepage: &lt; int&gt;**</span><span class="sxs-lookup"><span data-stu-id="d30ff-121">**--codepage:&lt;int&gt;**</span></span>|<span data-ttu-id="d30ff-122">**fsc.exe** 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-122">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="d30ff-123">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d30ff-123">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="d30ff-124">**--consolecolors**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="d30ff-124">**--consolecolors**[**+**&#124;**-**]</span></span>|<span data-ttu-id="d30ff-125">경고 및 오류 메시지를 색으로 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-125">Outputs warning and error messages in color.</span></span>|
|<span data-ttu-id="d30ff-126">**--교차 최적화**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="d30ff-126">**--crossoptimize**[**+**&#124;**-**]</span></span>|<span data-ttu-id="d30ff-127">크로스 모듈 최적화를 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-127">Enable or disable cross-module optimizations.</span></span>|
|<span data-ttu-id="d30ff-128">**--debug**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="d30ff-128">**--debug**[**+**&#124;**-**]</span></span><br /><br /><span data-ttu-id="d30ff-129">**--debug:**[**full**&#124;**pdbonly**&#124;**이식 가능한**&#124;**포함**]</span><span class="sxs-lookup"><span data-stu-id="d30ff-129">**--debug:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]</span></span><br /><br /><span data-ttu-id="d30ff-130">**-g**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="d30ff-130">**-g**[**+**&#124;**-**]</span></span><br /><br /><span data-ttu-id="d30ff-131">**-g:**[**full**&#124;**pdbonly**&#124;**이식 가능한**&#124;**포함**]</span><span class="sxs-lookup"><span data-stu-id="d30ff-131">**-g:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]</span></span>|<span data-ttu-id="d30ff-132">**fsc.exe** 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-132">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="d30ff-133">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d30ff-133">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="d30ff-134">**--define: &lt; 문자열&gt;**</span><span class="sxs-lookup"><span data-stu-id="d30ff-134">**--define:&lt;string&gt;**</span></span>|<span data-ttu-id="d30ff-135">**fsc.exe** 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-135">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="d30ff-136">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d30ff-136">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="d30ff-137">**--결정적**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="d30ff-137">**--deterministic**[**+**&#124;**-**]</span></span>|<span data-ttu-id="d30ff-138">결정적 어셈블리 (모듈 버전 GUID 및 타임 스탬프 포함)를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-138">Produces a deterministic assembly (including module version GUID and timestamp).</span></span>|
|<span data-ttu-id="d30ff-139">**--exec**</span><span class="sxs-lookup"><span data-stu-id="d30ff-139">**--exec**</span></span>|<span data-ttu-id="d30ff-140">파일을 로드 하거나 명령줄에 지정 된 스크립트 파일을 실행 한 후 F # interactive를 종료 하도록 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-140">Instructs F# interactive to exit after loading the files or running the script file given on the command line.</span></span>|
|<span data-ttu-id="d30ff-141">**--fullpaths**</span><span class="sxs-lookup"><span data-stu-id="d30ff-141">**--fullpaths**</span></span>|<span data-ttu-id="d30ff-142">**fsc.exe** 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-142">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="d30ff-143">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d30ff-143">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="d30ff-144">**--gui**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="d30ff-144">**--gui**[**+**&#124;**-**]</span></span>|<span data-ttu-id="d30ff-145">Windows Forms 이벤트 루프를 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-145">Enables or disables the Windows Forms event loop.</span></span> <span data-ttu-id="d30ff-146">기본값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-146">The default is enabled.</span></span>|
|<span data-ttu-id="d30ff-147">**--도움말**</span><span class="sxs-lookup"><span data-stu-id="d30ff-147">**--help**</span></span><br /><br /><span data-ttu-id="d30ff-148">**-?**</span><span class="sxs-lookup"><span data-stu-id="d30ff-148">**-?**</span></span>|<span data-ttu-id="d30ff-149">각 옵션에 대 한 간단한 설명 및 명령줄 구문을 표시 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-149">Used to display the command-line syntax and a brief description of each option.</span></span>|
|<span data-ttu-id="d30ff-150">**--lib: &lt; 폴더-목록&gt;**</span><span class="sxs-lookup"><span data-stu-id="d30ff-150">**--lib:&lt;folder-list&gt;**</span></span><br /><br /><span data-ttu-id="d30ff-151">**-I: &lt; 폴더-목록&gt;**</span><span class="sxs-lookup"><span data-stu-id="d30ff-151">**-I:&lt;folder-list&gt;**</span></span>|<span data-ttu-id="d30ff-152">**fsc.exe** 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-152">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="d30ff-153">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d30ff-153">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="d30ff-154">**--load: &lt; filename&gt;**</span><span class="sxs-lookup"><span data-stu-id="d30ff-154">**--load:&lt;filename&gt;**</span></span>|<span data-ttu-id="d30ff-155">시작 시 지정 된 소스 코드를 컴파일하고 컴파일된 F # 구문을 세션에 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-155">Compiles the given source code at startup and loads the compiled F# constructs into the session.</span></span>|
|<span data-ttu-id="d30ff-156">**--mlcompatibility**</span><span class="sxs-lookup"><span data-stu-id="d30ff-156">**--mlcompatibility**</span></span>|<span data-ttu-id="d30ff-157">**fsc.exe** 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-157">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="d30ff-158">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d30ff-158">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="d30ff-159">**--noframework**</span><span class="sxs-lookup"><span data-stu-id="d30ff-159">**--noframework**</span></span>|<span data-ttu-id="d30ff-160">**fsc.exe** 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-160">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="d30ff-161">자세한 내용은 [컴파일러 옵션](compiler-options.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d30ff-161">For more information, see [Compiler Options](compiler-options.md)</span></span>|
|<span data-ttu-id="d30ff-162">**--nologo**</span><span class="sxs-lookup"><span data-stu-id="d30ff-162">**--nologo**</span></span>|<span data-ttu-id="d30ff-163">**fsc.exe** 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-163">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="d30ff-164">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d30ff-164">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="d30ff-165">**--nowarn: &lt; warning-list&gt;**</span><span class="sxs-lookup"><span data-stu-id="d30ff-165">**--nowarn:&lt;warning-list&gt;**</span></span>|<span data-ttu-id="d30ff-166">**fsc.exe** 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-166">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="d30ff-167">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d30ff-167">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="d30ff-168">**--optimize**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="d30ff-168">**--optimize**[**+**&#124;**-**]</span></span>|<span data-ttu-id="d30ff-169">**fsc.exe** 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-169">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="d30ff-170">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d30ff-170">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="d30ff-171">**--preferreduilang: &lt; lang&gt;**</span><span class="sxs-lookup"><span data-stu-id="d30ff-171">**--preferreduilang:&lt;lang&gt;**</span></span>| <span data-ttu-id="d30ff-172">기본 출력 언어 문화권 이름 (예: es, ja-jp)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-172">Specifies the preferred output language culture name (for example, es-ES, ja-JP).</span></span> |
|<span data-ttu-id="d30ff-173">**--quiet**</span><span class="sxs-lookup"><span data-stu-id="d30ff-173">**--quiet**</span></span>|<span data-ttu-id="d30ff-174">**Stdout** 스트림에 대 한 F# 대화형 출력을 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-174">Suppress F# Interactive's output to the **stdout** stream.</span></span>|
|<span data-ttu-id="d30ff-175">**--인용구-debug**</span><span class="sxs-lookup"><span data-stu-id="d30ff-175">**--quotations-debug**</span></span>|<span data-ttu-id="d30ff-176">F # 인용 리터럴에서 파생 된 정의와 리플렉션 정의에서 파생 된 식에 대 한 추가 디버깅 정보를 내보내도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-176">Specifies that extra debugging information should be emitted for expressions that are derived from F# quotation literals and reflected definitions.</span></span> <span data-ttu-id="d30ff-177">디버그 정보는 F # 식 트리 노드의 사용자 지정 특성에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-177">The debug information is added to the custom attributes of an F# expression tree node.</span></span> <span data-ttu-id="d30ff-178">[코드 인용](code-quotations.md) 및 [Expr. customattributes](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr.html#CustomAttributes)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d30ff-178">See [Code Quotations](code-quotations.md) and [Expr.CustomAttributes](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr.html#CustomAttributes).</span></span>|
|<span data-ttu-id="d30ff-179">**--readline**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="d30ff-179">**--readline**[**+**&#124;**-**]</span></span>|<span data-ttu-id="d30ff-180">대화형 모드에서 탭 완성 기능을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-180">Enable or disable tab completion in interactive mode.</span></span>|
|<span data-ttu-id="d30ff-181">**--참조: &lt; 파일 이름&gt;**</span><span class="sxs-lookup"><span data-stu-id="d30ff-181">**--reference:&lt;filename&gt;**</span></span><br /><br /><span data-ttu-id="d30ff-182">**-r: &lt; 파일 이름&gt;**</span><span class="sxs-lookup"><span data-stu-id="d30ff-182">**-r:&lt;filename&gt;**</span></span>|<span data-ttu-id="d30ff-183">**fsc.exe** 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-183">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="d30ff-184">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d30ff-184">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="d30ff-185">**--tailcalls**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="d30ff-185">**--tailcalls**[**+**&#124;**-**]</span></span>|<span data-ttu-id="d30ff-186">Tail IL 명령을 사용 하거나 사용 하지 않도록 설정 하 여 tail 재귀 함수에 스택 프레임을 다시 사용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-186">Enable or disable the use of the tail IL instruction, which causes the stack frame to be reused for tail recursive functions.</span></span> <span data-ttu-id="d30ff-187">기본적으로 이 옵션은 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-187">This option is enabled by default.</span></span>|
|<span data-ttu-id="d30ff-188">**--targetprofile: &lt; 문자열&gt;**</span><span class="sxs-lookup"><span data-stu-id="d30ff-188">**--targetprofile:&lt;string&gt;**</span></span>|<span data-ttu-id="d30ff-189">이 어셈블리의 대상 프레임 워크 프로필을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-189">Specifies target framework profile of this assembly.</span></span> <span data-ttu-id="d30ff-190">유효한 값은 `mscorlib`, `netcore` 또는 `netstandard`입니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-190">Valid values are `mscorlib`, `netcore`, or `netstandard`.</span></span> <span data-ttu-id="d30ff-191">기본값은 `mscorlib`입니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-191">The default is `mscorlib`.</span></span>|
|<span data-ttu-id="d30ff-192">**--사용: &lt; 파일 이름&gt;**</span><span class="sxs-lookup"><span data-stu-id="d30ff-192">**--use:&lt;filename&gt;**</span></span>|<span data-ttu-id="d30ff-193">시작 시 지정 된 파일을 초기 입력으로 사용 하도록 인터프리터에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-193">Tells the interpreter to use the given file on startup as initial input.</span></span>|
|<span data-ttu-id="d30ff-194">**--utf8output**</span><span class="sxs-lookup"><span data-stu-id="d30ff-194">**--utf8output**</span></span>|<span data-ttu-id="d30ff-195">fsc.exe 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-195">Same as the fsc.exe compiler option.</span></span> <span data-ttu-id="d30ff-196">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d30ff-196">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="d30ff-197">**--경고: &lt; 경고 수준&gt;**</span><span class="sxs-lookup"><span data-stu-id="d30ff-197">**--warn:&lt;warning-level&gt;**</span></span>|<span data-ttu-id="d30ff-198">**fsc.exe** 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-198">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="d30ff-199">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d30ff-199">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="d30ff-200">**--warnaserror**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="d30ff-200">**--warnaserror**[**+**&#124;**-**]</span></span>|<span data-ttu-id="d30ff-201">**fsc.exe** 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-201">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="d30ff-202">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d30ff-202">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="d30ff-203">**--warnaserror**[ **+**&#124;**-** ]:\*\* &lt; int 목록 &gt; \*\*</span><span class="sxs-lookup"><span data-stu-id="d30ff-203">**--warnaserror**[**+**&#124;**-**]:**&lt;int-list&gt;**</span></span>|<span data-ttu-id="d30ff-204">**fsc.exe** 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-204">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="d30ff-205">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d30ff-205">For more information, see [Compiler Options](compiler-options.md).</span></span>|

## <a name="f-interactive-structured-printing"></a><span data-ttu-id="d30ff-206">F# 대화형 구조적 인쇄</span><span class="sxs-lookup"><span data-stu-id="d30ff-206">F# Interactive structured printing</span></span>

<span data-ttu-id="d30ff-207">F# 대화형 ( `dotnet fsi` )는 보고서 값에 대 한 [구조적 일반 텍스트 서식](plaintext-formatting.md) 의 확장 된 버전을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-207">F# Interactive (`dotnet fsi`) uses an extended version of [structured plain text formatting](plaintext-formatting.md) to report values.</span></span>

1. <span data-ttu-id="d30ff-208">`%A`일반 텍스트 서식의 모든 기능이 지원 되며 일부는 추가로 사용자 지정이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-208">All features of `%A` plain text formatting are supported, and some are additionally customizable.</span></span>

2. <span data-ttu-id="d30ff-209">출력 콘솔에서 색을 지 원하는 경우 인쇄는 색이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-209">Printing is colorized if colors are supported by the output console.</span></span>

3. <span data-ttu-id="d30ff-210">해당 문자열을 명시적으로 평가 하지 않으면 표시 되는 문자열의 길이에 제한이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-210">A limit is placed on the length of strings shown, unless you explicitly evaluate that string.</span></span>

4. <span data-ttu-id="d30ff-211">개체를 통해 사용자 정의 가능한 설정 집합을 사용할 수 있습니다 `fsi` .</span><span class="sxs-lookup"><span data-stu-id="d30ff-211">A set of user-definable settings is available via the `fsi` object.</span></span>

<span data-ttu-id="d30ff-212">보고 된 값에 대해 일반 텍스트 인쇄를 사용자 지정 하는 데 사용할 수 있는 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-212">The available settings to customize plain text printing for reported values are:</span></span>

```fsharp
open System.Globalization

fsi.FormatProvider <- CultureInfo("de-DE")  // control the default culture for primitives

fsi.PrintWidth <- 120        // Control the width used for structured printing

fsi.PrintDepth <- 10         // Control the maximum depth of nested printing

fsi.PrintLength <- 10        // Control the length of lists and arrays

fsi.PrintSize <- 100         // Control the maximum overall object count

fsi.ShowProperties <- false  // Control whether properties of .NET objects are shown by default

fsi.ShowIEnumerable <- false // Control whether sequence values are expanded by default

fsi.ShowDeclarationValues <- false // Control whether values are shown for declaration outputs
```

### <a name="customize-with-addprinter-and-addprinttransformer"></a><span data-ttu-id="d30ff-213">및를 사용 하 여 사용자 지정 `AddPrinter``AddPrintTransformer`</span><span class="sxs-lookup"><span data-stu-id="d30ff-213">Customize with `AddPrinter` and `AddPrintTransformer`</span></span>

<span data-ttu-id="d30ff-214">및를 사용 하 여 F# 대화형 출력의 인쇄를 사용자 지정할 수 있습니다 `fsi.AddPrinter` `fsi.AddPrintTransformer` .</span><span class="sxs-lookup"><span data-stu-id="d30ff-214">Printing in F# Interactive outputs can be customized by using `fsi.AddPrinter` and `fsi.AddPrintTransformer`.</span></span>
<span data-ttu-id="d30ff-215">첫 번째 함수는 개체의 인쇄를 바꿀 텍스트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-215">The first function gives text to replace the printing of an object.</span></span> <span data-ttu-id="d30ff-216">두 번째 함수는 대신 표시할 서로게이트 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-216">The second function returns a surrogate object to display instead.</span></span> <span data-ttu-id="d30ff-217">예를 들어 다음 F # 코드를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="d30ff-217">For example, consider the following F# code:</span></span>

```fsharp
open System

fsi.AddPrinter<DateTime>(fun dt -> dt.ToString("s"))

type DateAndLabel =
    { Date: DateTime
      Label: string  }

let newYearsDay1999 =
    { Date = DateTime(1999, 1, 1)
      Label = "New Year" }
```

<span data-ttu-id="d30ff-218">F# 대화형에서 예제를 실행 하는 경우 형식 지정 옵션 집합을 기반으로 출력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-218">If you execute the example in F# Interactive, it outputs based on the formatting option set.</span></span> <span data-ttu-id="d30ff-219">이 경우 날짜 및 시간의 형식에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-219">In this case, it affects the formatting of date and time:</span></span>

```console
type DateAndLabel =
  { Date: DateTime
    Label: string }
val newYearsDay1999 : DateAndLabel = { Date = 1999-01-01T00:00:00
                                       Label = "New Year" }
```

<span data-ttu-id="d30ff-220">`fsi.AddPrintTransformer` 를 사용 하 여 인쇄를 위한 서로게이트 개체를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-220">`fsi.AddPrintTransformer` can be used to give a surrogate object for printing:</span></span>

```fsharp
type MyList(values: int list) =
    member _.Values = values

fsi.AddPrintTransformer(fun (x:MyList) -> box x.Values)

let x = MyList([1..10])
```

<span data-ttu-id="d30ff-221">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-221">This outputs:</span></span>

```console
val x : MyList = [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
```

<span data-ttu-id="d30ff-222">에 전달 된 변환기 함수가를 반환 하는 경우 `fsi.AddPrintTransformer` `null` 인쇄 변환기는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-222">If the transformer function passed to `fsi.AddPrintTransformer` returns `null`, then the print transformer is ignored.</span></span>
<span data-ttu-id="d30ff-223">형식으로 시작 하 여 입력 값을 필터링 하는 데 사용할 수 있습니다 `obj` .</span><span class="sxs-lookup"><span data-stu-id="d30ff-223">This can be used to filter any input value by starting with type `obj`.</span></span>  <span data-ttu-id="d30ff-224">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="d30ff-224">For example:</span></span>

```fsharp
fsi.AddPrintTransformer(fun (x:obj) ->
    match x with
    | :? string as s when s = "beep" -> box ["quack"; "quack"; "quack"]
    | _ -> null)

let y = "beep"
```

<span data-ttu-id="d30ff-225">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-225">This outputs:</span></span>

```console
val y : string = ["quack"; "quack"; "quack"]
```

## <a name="related-topics"></a><span data-ttu-id="d30ff-226">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d30ff-226">Related topics</span></span>

|<span data-ttu-id="d30ff-227">제목</span><span class="sxs-lookup"><span data-stu-id="d30ff-227">Title</span></span>|<span data-ttu-id="d30ff-228">Description</span><span class="sxs-lookup"><span data-stu-id="d30ff-228">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="d30ff-229">컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="d30ff-229">Compiler Options</span></span>](compiler-options.md)|<span data-ttu-id="d30ff-230">**fsc.exe**F # 컴파일러에 사용할 수 있는 명령줄 옵션에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d30ff-230">Describes command-line options available for the F# compiler, **fsc.exe**.</span></span>|
