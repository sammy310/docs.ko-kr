---
title: 대화형 옵션
description: F# 대화형 fsi.exe에서 지 원하는 명령줄 옵션에 대해 알아봅니다.
ms.date: 07/22/2020
ms.openlocfilehash: f9932cac24fad187c332306968fb13981912e80a
ms.sourcegitcommit: 09bad6ec0cbf18be7cd7f62e77286d305a18b607
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2020
ms.locfileid: "87795465"
---
# <a name="f-interactive-options"></a><span data-ttu-id="21e98-103">F# 대화형 옵션</span><span class="sxs-lookup"><span data-stu-id="21e98-103">F# Interactive options</span></span>

<span data-ttu-id="21e98-104">이 문서에서는 F# 대화형에서 지 원하는 명령줄 옵션을 설명 합니다 `fsi.exe` .</span><span class="sxs-lookup"><span data-stu-id="21e98-104">This article describes the command-line options supported by F# Interactive, `fsi.exe`.</span></span> <span data-ttu-id="21e98-105">F# 대화형은 F # 컴파일러와 동일한 명령줄 옵션을 여러 개 사용할 수 있지만 몇 가지 추가 옵션도 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-105">F# Interactive accepts many of the same command line options as the F# compiler, but also accepts some additional options.</span></span>

## <a name="use-f-interactive-for-scripting"></a><span data-ttu-id="21e98-106">스크립팅에 F# 대화형 사용</span><span class="sxs-lookup"><span data-stu-id="21e98-106">Use F# Interactive for scripting</span></span>

<span data-ttu-id="21e98-107">F# 대화형는 `dotnet fsi` 대화형으로 실행 하거나 명령줄에서 실행 하 여 스크립트를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-107">F# Interactive, `dotnet fsi`, can be launched interactively, or it can be launched from the command line to run a script.</span></span> <span data-ttu-id="21e98-108">명령줄 구문은</span><span class="sxs-lookup"><span data-stu-id="21e98-108">The command line syntax is</span></span>

```dotnetcli
dotnet fsi [options] [ script-file [arguments] ]
```

<span data-ttu-id="21e98-109">F # 스크립트 파일의 파일 확장명은 `.fsx` 입니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-109">The file extension for F# script files is `.fsx`.</span></span>

## <a name="table-of-f-interactive-options"></a><span data-ttu-id="21e98-110">F# 대화형 옵션 표</span><span class="sxs-lookup"><span data-stu-id="21e98-110">Table of F# Interactive Options</span></span>

<span data-ttu-id="21e98-111">다음 표에서는 F# 대화형에서 지 원하는 옵션을 요약 하 여 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-111">The following table summarizes the options supported by F# Interactive.</span></span> <span data-ttu-id="21e98-112">명령줄에서 또는 Visual Studio IDE를 통해 이러한 옵션을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-112">You can set these options on the command-line or through the Visual Studio IDE.</span></span> <span data-ttu-id="21e98-113">Visual Studio IDE에서 이러한 옵션을 설정 하려면 **도구** 메뉴를 열고 **옵션 ...** 을 선택한 다음 **F # 도구** 노드를 확장 하 고 **F# 대화형**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-113">To set these options in the Visual Studio IDE, open the **Tools** menu, select **Options...**, then expand the **F# Tools** node and select **F# Interactive**.</span></span>

<span data-ttu-id="21e98-114">목록 요소가 F# 대화형 옵션 인수에 표시 되는 경우 목록 요소는 세미콜론 ()으로 구분 됩니다 `;` .</span><span class="sxs-lookup"><span data-stu-id="21e98-114">Where lists appear in F# Interactive option arguments, list elements are separated by semicolons (`;`).</span></span>

|<span data-ttu-id="21e98-115">옵션</span><span class="sxs-lookup"><span data-stu-id="21e98-115">Option</span></span>|<span data-ttu-id="21e98-116">설명</span><span class="sxs-lookup"><span data-stu-id="21e98-116">Description</span></span>|
|------|-----------|
|**--**|<span data-ttu-id="21e98-117">**Fsi.exe my.application.commandlineargs**를 사용 하 여 코드에서 액세스할 수 있는 F # 프로그램 또는 스크립트에 대 한 명령줄 인수로 나머지 인수를 처리 하도록 F# 대화형에 지시 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-117">Used to instruct F# Interactive to treat remaining arguments as command line arguments to the F# program or script, which you can access in code by using the list **fsi.CommandLineArgs**.</span></span>|
|<span data-ttu-id="21e98-118">**--확인**됨 [ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="21e98-118">**--checked**[**+**&#124;**-**]</span></span>|<span data-ttu-id="21e98-119">**fsc.exe** 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-119">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="21e98-120">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21e98-120">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="21e98-121">**--codepage: &lt; int&gt;**</span><span class="sxs-lookup"><span data-stu-id="21e98-121">**--codepage:&lt;int&gt;**</span></span>|<span data-ttu-id="21e98-122">**fsc.exe** 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-122">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="21e98-123">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21e98-123">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="21e98-124">**--consolecolors**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="21e98-124">**--consolecolors**[**+**&#124;**-**]</span></span>|<span data-ttu-id="21e98-125">경고 및 오류 메시지를 색으로 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-125">Outputs warning and error messages in color.</span></span>|
|<span data-ttu-id="21e98-126">**--교차 최적화**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="21e98-126">**--crossoptimize**[**+**&#124;**-**]</span></span>|<span data-ttu-id="21e98-127">크로스 모듈 최적화를 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-127">Enable or disable cross-module optimizations.</span></span>|
|<span data-ttu-id="21e98-128">**--debug**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="21e98-128">**--debug**[**+**&#124;**-**]</span></span><br /><br /><span data-ttu-id="21e98-129">**--debug:**[**full**&#124;**pdbonly**&#124;**이식 가능한**&#124;**포함**]</span><span class="sxs-lookup"><span data-stu-id="21e98-129">**--debug:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]</span></span><br /><br /><span data-ttu-id="21e98-130">**-g**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="21e98-130">**-g**[**+**&#124;**-**]</span></span><br /><br /><span data-ttu-id="21e98-131">**-g:**[**full**&#124;**pdbonly**&#124;**이식 가능한**&#124;**포함**]</span><span class="sxs-lookup"><span data-stu-id="21e98-131">**-g:**[**full**&#124;**pdbonly**&#124;**portable**&#124;**embedded**]</span></span>|<span data-ttu-id="21e98-132">**fsc.exe** 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-132">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="21e98-133">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21e98-133">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="21e98-134">**--define: &lt; 문자열&gt;**</span><span class="sxs-lookup"><span data-stu-id="21e98-134">**--define:&lt;string&gt;**</span></span>|<span data-ttu-id="21e98-135">**fsc.exe** 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-135">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="21e98-136">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21e98-136">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="21e98-137">**--결정적**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="21e98-137">**--deterministic**[**+**&#124;**-**]</span></span>|<span data-ttu-id="21e98-138">결정적 어셈블리 (모듈 버전 GUID 및 타임 스탬프 포함)를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-138">Produces a deterministic assembly (including module version GUID and timestamp).</span></span>|
|<span data-ttu-id="21e98-139">**--exec**</span><span class="sxs-lookup"><span data-stu-id="21e98-139">**--exec**</span></span>|<span data-ttu-id="21e98-140">파일을 로드 하거나 명령줄에 지정 된 스크립트 파일을 실행 한 후 F # interactive를 종료 하도록 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-140">Instructs F# interactive to exit after loading the files or running the script file given on the command line.</span></span>|
|<span data-ttu-id="21e98-141">**--fullpaths**</span><span class="sxs-lookup"><span data-stu-id="21e98-141">**--fullpaths**</span></span>|<span data-ttu-id="21e98-142">**fsc.exe** 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-142">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="21e98-143">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21e98-143">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="21e98-144">**--gui**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="21e98-144">**--gui**[**+**&#124;**-**]</span></span>|<span data-ttu-id="21e98-145">Windows Forms 이벤트 루프를 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-145">Enables or disables the Windows Forms event loop.</span></span> <span data-ttu-id="21e98-146">기본값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-146">The default is enabled.</span></span>|
|<span data-ttu-id="21e98-147">**--도움말**</span><span class="sxs-lookup"><span data-stu-id="21e98-147">**--help**</span></span><br /><br /><span data-ttu-id="21e98-148">**-?**</span><span class="sxs-lookup"><span data-stu-id="21e98-148">**-?**</span></span>|<span data-ttu-id="21e98-149">명령줄 구문 및 각 옵션에 대 한 간단한 설명을 표시 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-149">Used to display the command line syntax and a brief description of each option.</span></span>|
|<span data-ttu-id="21e98-150">**--lib: &lt; 폴더-목록&gt;**</span><span class="sxs-lookup"><span data-stu-id="21e98-150">**--lib:&lt;folder-list&gt;**</span></span><br /><br /><span data-ttu-id="21e98-151">**-I: &lt; 폴더-목록&gt;**</span><span class="sxs-lookup"><span data-stu-id="21e98-151">**-I:&lt;folder-list&gt;**</span></span>|<span data-ttu-id="21e98-152">**fsc.exe** 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-152">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="21e98-153">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21e98-153">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="21e98-154">**--load: &lt; filename&gt;**</span><span class="sxs-lookup"><span data-stu-id="21e98-154">**--load:&lt;filename&gt;**</span></span>|<span data-ttu-id="21e98-155">시작 시 지정 된 소스 코드를 컴파일하고 컴파일된 F # 구문을 세션에 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-155">Compiles the given source code at startup and loads the compiled F# constructs into the session.</span></span> <span data-ttu-id="21e98-156">대상 소스에 **#use** 또는 **#load**같은 스크립팅 지시문이 포함 되어 있는 경우-- **load** 또는 **#load**대신-- **use** 또는 **#use** 를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-156">If the target source contains scripting directives such as **#use** or **#load**, then you must use **--use** or **#use** instead of **--load** or **#load**.</span></span>|
|<span data-ttu-id="21e98-157">**--mlcompatibility**</span><span class="sxs-lookup"><span data-stu-id="21e98-157">**--mlcompatibility**</span></span>|<span data-ttu-id="21e98-158">**fsc.exe** 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-158">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="21e98-159">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21e98-159">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="21e98-160">**--noframework**</span><span class="sxs-lookup"><span data-stu-id="21e98-160">**--noframework**</span></span>|<span data-ttu-id="21e98-161">**fsc.exe** 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-161">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="21e98-162">자세한 내용은 [컴파일러 옵션](compiler-options.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21e98-162">For more information, see [Compiler Options](compiler-options.md)</span></span>|
|<span data-ttu-id="21e98-163">**--nologo**</span><span class="sxs-lookup"><span data-stu-id="21e98-163">**--nologo**</span></span>|<span data-ttu-id="21e98-164">**fsc.exe** 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-164">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="21e98-165">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21e98-165">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="21e98-166">**--nowarn: &lt; warning-list&gt;**</span><span class="sxs-lookup"><span data-stu-id="21e98-166">**--nowarn:&lt;warning-list&gt;**</span></span>|<span data-ttu-id="21e98-167">**fsc.exe** 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-167">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="21e98-168">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21e98-168">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="21e98-169">**--optimize**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="21e98-169">**--optimize**[**+**&#124;**-**]</span></span>|<span data-ttu-id="21e98-170">**fsc.exe** 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-170">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="21e98-171">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21e98-171">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="21e98-172">**--preferreduilang: &lt; lang&gt;**</span><span class="sxs-lookup"><span data-stu-id="21e98-172">**--preferreduilang:&lt;lang&gt;**</span></span>| <span data-ttu-id="21e98-173">기본 출력 언어 문화권 이름 (예: es, ja-jp)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-173">Specifies the preferred output language culture name (for example, es-ES, ja-JP).</span></span> |
|<span data-ttu-id="21e98-174">**--quiet**</span><span class="sxs-lookup"><span data-stu-id="21e98-174">**--quiet**</span></span>|<span data-ttu-id="21e98-175">**Stdout** 스트림에 대 한 F# 대화형 출력을 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-175">Suppress F# Interactive's output to the **stdout** stream.</span></span>|
|<span data-ttu-id="21e98-176">**--인용구-debug**</span><span class="sxs-lookup"><span data-stu-id="21e98-176">**--quotations-debug**</span></span>|<span data-ttu-id="21e98-177">F # 인용 리터럴에서 파생 된 정의와 리플렉션 정의에서 파생 된 식에 대 한 추가 디버깅 정보를 내보내도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-177">Specifies that extra debugging information should be emitted for expressions that are derived from F# quotation literals and reflected definitions.</span></span> <span data-ttu-id="21e98-178">디버그 정보는 F # 식 트리 노드의 사용자 지정 특성에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-178">The debug information is added to the custom attributes of an F# expression tree node.</span></span> <span data-ttu-id="21e98-179">[코드 인용](code-quotations.md) 및 [Expr. customattributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21e98-179">See [Code Quotations](code-quotations.md) and [Expr.CustomAttributes](https://msdn.microsoft.com/library/eb89943f-5f5b-474e-b125-030ca412edb3).</span></span>|
|<span data-ttu-id="21e98-180">**--readline**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="21e98-180">**--readline**[**+**&#124;**-**]</span></span>|<span data-ttu-id="21e98-181">대화형 모드에서 탭 완성 기능을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-181">Enable or disable tab completion in interactive mode.</span></span>|
|<span data-ttu-id="21e98-182">**--참조: &lt; 파일 이름&gt;**</span><span class="sxs-lookup"><span data-stu-id="21e98-182">**--reference:&lt;filename&gt;**</span></span><br /><br /><span data-ttu-id="21e98-183">**-r: &lt; 파일 이름&gt;**</span><span class="sxs-lookup"><span data-stu-id="21e98-183">**-r:&lt;filename&gt;**</span></span>|<span data-ttu-id="21e98-184">**fsc.exe** 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-184">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="21e98-185">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21e98-185">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="21e98-186">**--tailcalls**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="21e98-186">**--tailcalls**[**+**&#124;**-**]</span></span>|<span data-ttu-id="21e98-187">Tail IL 명령을 사용 하거나 사용 하지 않도록 설정 하 여 tail 재귀 함수에 스택 프레임을 다시 사용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-187">Enable or disable the use of the tail IL instruction, which causes the stack frame to be reused for tail recursive functions.</span></span> <span data-ttu-id="21e98-188">기본적으로 이 옵션은 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-188">This option is enabled by default.</span></span>|
|<span data-ttu-id="21e98-189">**--targetprofile: &lt; 문자열&gt;**</span><span class="sxs-lookup"><span data-stu-id="21e98-189">**--targetprofile:&lt;string&gt;**</span></span>|<span data-ttu-id="21e98-190">이 어셈블리의 대상 프레임 워크 프로필을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-190">Specifies target framework profile of this assembly.</span></span> <span data-ttu-id="21e98-191">유효한 값은 mscorlib, microsoft.netcore.portable.compatibility 또는 microsoft.netcore.portable.compatibility입니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-191">Valid values are mscorlib, netcore or netstandard.</span></span>  <span data-ttu-id="21e98-192">기본값은 mscorlib입니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-192">The default is mscorlib.</span></span>|
|<span data-ttu-id="21e98-193">**--사용: &lt; 파일 이름&gt;**</span><span class="sxs-lookup"><span data-stu-id="21e98-193">**--use:&lt;filename&gt;**</span></span>|<span data-ttu-id="21e98-194">시작 시 지정 된 파일을 초기 입력으로 사용 하도록 인터프리터에 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-194">Tells the interpreter to use the given file on startup as initial input.</span></span>|
|<span data-ttu-id="21e98-195">**--utf8output**</span><span class="sxs-lookup"><span data-stu-id="21e98-195">**--utf8output**</span></span>|<span data-ttu-id="21e98-196">fsc.exe 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-196">Same as the fsc.exe compiler option.</span></span> <span data-ttu-id="21e98-197">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21e98-197">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="21e98-198">**--경고: &lt; 경고 수준&gt;**</span><span class="sxs-lookup"><span data-stu-id="21e98-198">**--warn:&lt;warning-level&gt;**</span></span>|<span data-ttu-id="21e98-199">**fsc.exe** 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-199">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="21e98-200">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21e98-200">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="21e98-201">**--warnaserror**[ **+**&#124;**-** ]</span><span class="sxs-lookup"><span data-stu-id="21e98-201">**--warnaserror**[**+**&#124;**-**]</span></span>|<span data-ttu-id="21e98-202">**fsc.exe** 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-202">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="21e98-203">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21e98-203">For more information, see [Compiler Options](compiler-options.md).</span></span>|
|<span data-ttu-id="21e98-204">**--warnaserror**[ **+**&#124;**-** ]:\*\* &lt; int 목록 &gt; \*\*</span><span class="sxs-lookup"><span data-stu-id="21e98-204">**--warnaserror**[**+**&#124;**-**]:**&lt;int-list&gt;**</span></span>|<span data-ttu-id="21e98-205">**fsc.exe** 컴파일러 옵션과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-205">Same as the **fsc.exe** compiler option.</span></span> <span data-ttu-id="21e98-206">자세한 내용은 [컴파일러 옵션](compiler-options.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="21e98-206">For more information, see [Compiler Options](compiler-options.md).</span></span>|

## <a name="f-interactive-structured-printing"></a><span data-ttu-id="21e98-207">F# 대화형 구조적 인쇄</span><span class="sxs-lookup"><span data-stu-id="21e98-207">F# Interactive structured printing</span></span>

<span data-ttu-id="21e98-208">F# 대화형 ( `dotnet fsi` )는 보고서 값에 대 한 [구조적 일반 텍스트 서식](plaintext-formatting.md) 의 확장 된 버전을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-208">F# Interactive (`dotnet fsi`) uses an extended version of [structured plain text formatting](plaintext-formatting.md) to report values.</span></span>

1. <span data-ttu-id="21e98-209">`%A`일반 텍스트 서식의 모든 기능이 지원 되며 일부는 추가로 사용자 지정이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-209">All features of `%A` plain text formatting are supported, and some are additionally customizable.</span></span>

2. <span data-ttu-id="21e98-210">출력 콘솔에서 색을 지 원하는 경우 인쇄는 색이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-210">Printing is colorized if colors are supported by the output console.</span></span>

3. <span data-ttu-id="21e98-211">해당 문자열을 명시적으로 평가 하지 않으면 표시 되는 문자열의 길이에 제한이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-211">A limit is placed on the length of strings shown, unless you explicitly evaluate that string.</span></span>

4. <span data-ttu-id="21e98-212">개체를 통해 사용자 정의 가능한 설정 집합을 사용할 수 있습니다 `fsi` .</span><span class="sxs-lookup"><span data-stu-id="21e98-212">A set of user-definable settings are available via the `fsi` object.</span></span>

<span data-ttu-id="21e98-213">보고 된 값에 대해 일반 텍스트 인쇄를 사용자 지정 하는 데 사용할 수 있는 설정은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-213">The available settings to customize plain text printing for reported values are:</span></span>

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

### <a name="customize-with-addprinter-and-addprinttransformer"></a><span data-ttu-id="21e98-214">및를 사용 하 여 사용자 지정 `AddPrinter``AddPrintTransformer`</span><span class="sxs-lookup"><span data-stu-id="21e98-214">Customize with `AddPrinter` and `AddPrintTransformer`</span></span>

<span data-ttu-id="21e98-215">및를 사용 하 여 F# 대화형 출력의 인쇄를 사용자 지정할 수 있습니다 `fsi.AddPrinter` `fsi.AddPrintTransformer` .</span><span class="sxs-lookup"><span data-stu-id="21e98-215">Printing in F# Interactive outputs can be customized by using `fsi.AddPrinter` and `fsi.AddPrintTransformer`.</span></span>
<span data-ttu-id="21e98-216">첫 번째 함수는 개체의 인쇄를 바꿀 텍스트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-216">The first function gives text to replace the printing of an object.</span></span> <span data-ttu-id="21e98-217">두 번째 함수는 대신 표시할 서로게이트 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-217">The second function returns a surrogate object to display instead.</span></span> <span data-ttu-id="21e98-218">예를 들어 다음 F # 코드를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="21e98-218">For example, consider the following F# code:</span></span>

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

<span data-ttu-id="21e98-219">F# 대화형에서 예제를 실행 하는 경우 형식 지정 옵션 집합을 기반으로 출력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-219">If you execute the example in F# Interactive, it outputs based on the formatting option set.</span></span> <span data-ttu-id="21e98-220">이 경우 날짜 및 시간의 형식에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-220">In this case, it affects the formatting of date and time:</span></span>

```console
type DateAndLabel =
  { Date: DateTime
    Label: string }
val newYearsDay1999 : DateAndLabel = { Date = 1999-01-01T00:00:00
                                       Label = "New Year" }
```

<span data-ttu-id="21e98-221">`fsi.AddPrintTransformer`를 사용 하 여 인쇄를 위한 서로게이트 개체를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-221">`fsi.AddPrintTransformer` can be used to give a surrogate object for printing:</span></span>

```fsharp
type MyList(values: int list) =
    member _.Values = values

fsi.AddPrintTransformer(fun (x:MyList) -> box x.Values)

let x = MyList([1..10])
```

<span data-ttu-id="21e98-222">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-222">This outputs:</span></span>

```console
val x : MyList = [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
```

<span data-ttu-id="21e98-223">에 전달 된 변환기 함수가를 반환 하는 경우 `fsi.AddPrintTransformer` `null` 인쇄 변환기는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-223">If the transformer function passed to `fsi.AddPrintTransformer` returns `null`, then the print transformer is ignored.</span></span>
<span data-ttu-id="21e98-224">형식으로 시작 하 여 입력 값을 필터링 하는 데 사용할 수 있습니다 `obj` .</span><span class="sxs-lookup"><span data-stu-id="21e98-224">This can be used to filter any input value by starting with type `obj`.</span></span>  <span data-ttu-id="21e98-225">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="21e98-225">For example:</span></span>

```fsharp
fsi.AddPrintTransformer(fun (x:obj) ->
    match x with
    | :? string as s when s = "beep" -> box ["quack"; "quack"; "quack"]
    | _ -> null)

let y = "beep"
```

<span data-ttu-id="21e98-226">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-226">This outputs:</span></span>

```console
val y : string = ["quack"; "quack"; "quack"]
```

## <a name="related-topics"></a><span data-ttu-id="21e98-227">관련 항목</span><span class="sxs-lookup"><span data-stu-id="21e98-227">Related topics</span></span>

|<span data-ttu-id="21e98-228">제목</span><span class="sxs-lookup"><span data-stu-id="21e98-228">Title</span></span>|<span data-ttu-id="21e98-229">설명</span><span class="sxs-lookup"><span data-stu-id="21e98-229">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="21e98-230">컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="21e98-230">Compiler Options</span></span>](compiler-options.md)|<span data-ttu-id="21e98-231">**fsc.exe**F # 컴파일러에 사용할 수 있는 명령줄 옵션에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="21e98-231">Describes command line options available for the F# compiler, **fsc.exe**.</span></span>|
