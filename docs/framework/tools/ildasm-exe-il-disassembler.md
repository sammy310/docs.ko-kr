---
title: Ildasm.exe(IL 디스어셈블러)
description: Ildasm.exe(IL 디스어셈블러)는 IL(중간 언어) 코드가 포함된 PE(이식 가능한 실행 파일) 파일을 가져와서 Ilasm.exe를 위한 텍스트 파일을 만듭니다.
ms.date: 03/30/2017
helpviewer_keywords:
- PE files, MSIL Disassembler
- portable executable files, MSIL Disassembler
- Ildasm.exe
- MSIL Disassembler
- text files produced by MSIL Disassembler
- disassembling file for MSIL Assembler input
ms.assetid: db27f6b2-f1ec-499e-be3a-7eecf95ca42b
ms.openlocfilehash: 6f2611488e7f653783cab833ad47131978bf74aa
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166836"
---
# <a name="ildasmexe-il-disassembler"></a><span data-ttu-id="d507b-103">Ildasm.exe(IL 디스어셈블러)</span><span class="sxs-lookup"><span data-stu-id="d507b-103">Ildasm.exe (IL Disassembler)</span></span>

<span data-ttu-id="d507b-104">IL 디스어셈블러는 IL 어셈블러(*Ilasm.exe*)의 자매 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-104">The IL Disassembler is a companion tool to the IL Assembler (*Ilasm.exe*).</span></span> <span data-ttu-id="d507b-105">*Ildasm.exe*는 IL(intermediate language) 코드가 포함된 PE(이식 가능한 실행) 파일을 가져와서 *Ildasm.exe*에 입력하기에 적합한 텍스트 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-105">*Ildasm.exe* takes a portable executable (PE) file that contains intermediate language (IL) code and creates a text file suitable as input to *Ilasm.exe*.</span></span>

<span data-ttu-id="d507b-106">이 도구는 자동으로 Visual Studio와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-106">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="d507b-107">이 도구를 실행하려면 Visual Studio용 개발자 명령 프롬프트(또는 Windows 7의 Visual Studio 명령 프롬프트)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-107">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="d507b-108">자세한 내용은 [명령 프롬프트](developer-command-prompt-for-vs.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d507b-108">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>

<span data-ttu-id="d507b-109">명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-109">At the command prompt, type the following:</span></span>

## <a name="syntax"></a><span data-ttu-id="d507b-110">구문</span><span class="sxs-lookup"><span data-stu-id="d507b-110">Syntax</span></span>

```console
ildasm [options] [PEfilename] [options]
```

## <a name="parameters"></a><span data-ttu-id="d507b-111">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d507b-111">Parameters</span></span>

<span data-ttu-id="d507b-112">*.exe*, *.dll*, *.obj*, *.lib* 및 *.winmd* 파일에 사용할 수 있는 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-112">The following options are available for *.exe*, *.dll*, *.obj*, *.lib*, and *.winmd* files.</span></span>

| <span data-ttu-id="d507b-113">옵션</span><span class="sxs-lookup"><span data-stu-id="d507b-113">Option</span></span> | <span data-ttu-id="d507b-114">설명</span><span class="sxs-lookup"><span data-stu-id="d507b-114">Description</span></span> |
| ------ | ----------- |
|<span data-ttu-id="d507b-115">**/out=** `filename`</span><span class="sxs-lookup"><span data-stu-id="d507b-115">**/out=** `filename`</span></span>|<span data-ttu-id="d507b-116">결과를 그래픽 사용자 인터페이스에 표시하지 않고 지정된 `filename`을 사용하여 출력 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-116">Creates an output file with the specified `filename`, rather than displaying the results in a graphical user interface.</span></span>|
|<span data-ttu-id="d507b-117">**/rtf**</span><span class="sxs-lookup"><span data-stu-id="d507b-117">**/rtf**</span></span>|<span data-ttu-id="d507b-118">서식 있는 텍스트로 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-118">Produces output in rich text format.</span></span> <span data-ttu-id="d507b-119">**/text** 옵션과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-119">Invalid with the **/text** option.</span></span>|
|<span data-ttu-id="d507b-120">**/text**</span><span class="sxs-lookup"><span data-stu-id="d507b-120">**/text**</span></span>|<span data-ttu-id="d507b-121">결과를 그래픽 사용자 인터페이스에 표시하거나 출력 파일로 표시하지 않고 콘솔 창에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-121">Displays the results to the console window, rather than in a graphical user interface or as an output file.</span></span>|
|<span data-ttu-id="d507b-122">**/html**</span><span class="sxs-lookup"><span data-stu-id="d507b-122">**/html**</span></span>|<span data-ttu-id="d507b-123">HTML 형식으로 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-123">Produces output in HTML format.</span></span> <span data-ttu-id="d507b-124">**/output** 옵션으로만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-124">Valid with the **/output** option only.</span></span>|
|<span data-ttu-id="d507b-125">**/?**</span><span class="sxs-lookup"><span data-stu-id="d507b-125">**/?**</span></span>|<span data-ttu-id="d507b-126">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-126">Displays the command syntax and options for the tool.</span></span>|

<span data-ttu-id="d507b-127">*.exe*, *.dll* 및 *.winmd* 파일에 사용할 수 있는 추가 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-127">The following additional options are available for *.exe*, *.dll*, and *.winmd* files.</span></span>

| <span data-ttu-id="d507b-128">옵션</span><span class="sxs-lookup"><span data-stu-id="d507b-128">Option</span></span> | <span data-ttu-id="d507b-129">설명</span><span class="sxs-lookup"><span data-stu-id="d507b-129">Description</span></span> |
| ------ | ----------- |
|<span data-ttu-id="d507b-130">**/bytes**</span><span class="sxs-lookup"><span data-stu-id="d507b-130">**/bytes**</span></span>|<span data-ttu-id="d507b-131">16진수 형식의 실제 바이트 수를 명령 주석으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-131">Shows actual bytes, in hexadecimal format, as instruction comments.</span></span>|
|<span data-ttu-id="d507b-132">**/caverbal**</span><span class="sxs-lookup"><span data-stu-id="d507b-132">**/caverbal**</span></span>|<span data-ttu-id="d507b-133">사용자 지정 특성 blob을 일반 텍스트 형식으로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-133">Produces custom attribute blobs in verbal form.</span></span> <span data-ttu-id="d507b-134">기본값은 이진 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-134">The default is binary form.</span></span>|
|<span data-ttu-id="d507b-135">**/linenum**</span><span class="sxs-lookup"><span data-stu-id="d507b-135">**/linenum**</span></span>|<span data-ttu-id="d507b-136">원본 소스 줄에 대한 참조를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-136">Includes references to original source lines.</span></span>|
|<span data-ttu-id="d507b-137">**/nobar**</span><span class="sxs-lookup"><span data-stu-id="d507b-137">**/nobar**</span></span>|<span data-ttu-id="d507b-138">디스어셈블리 진행률 표시줄 팝업 창을 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-138">Suppresses the disassembly progress indicator pop-up window.</span></span>|
|<span data-ttu-id="d507b-139">**/noca**</span><span class="sxs-lookup"><span data-stu-id="d507b-139">**/noca**</span></span>|<span data-ttu-id="d507b-140">사용자 지정 특성 출력을 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-140">Suppresses the output of custom attributes.</span></span>|
|<span data-ttu-id="d507b-141">**/project**</span><span class="sxs-lookup"><span data-stu-id="d507b-141">**/project**</span></span>|<span data-ttu-id="d507b-142">메타데이터를 기본 Windows 런타임에서 표시되는 방식 대신, 관리 코드에 표시되는 방식으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-142">Displays metadata the way it appears to managed code, instead of the way it appears in the native Windows Runtime.</span></span> <span data-ttu-id="d507b-143">만약 `PEfilename`이 Windows 메타데이터( *.winmd*) 파일이 아니라면, 이 옵션은 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-143">If `PEfilename` is not a Windows metadata (*.winmd*) file, this option has no effect.</span></span> <span data-ttu-id="d507b-144">[Windows 스토어 앱 및 Windows 런타임에 대한 .NET Framework 지원](../../standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d507b-144">See [.NET Framework Support for Windows Store Apps and Windows Runtime](../../standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md).</span></span>|
|<span data-ttu-id="d507b-145">**/pubonly**</span><span class="sxs-lookup"><span data-stu-id="d507b-145">**/pubonly**</span></span>|<span data-ttu-id="d507b-146">공용 형식 및 멤버만 디스어셈블합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-146">Disassembles only public types and members.</span></span> <span data-ttu-id="d507b-147">**/visibility:PUB**와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-147">Equivalent to **/visibility:PUB**.</span></span>|
|<span data-ttu-id="d507b-148">**/quoteallnames**</span><span class="sxs-lookup"><span data-stu-id="d507b-148">**/quoteallnames**</span></span>|<span data-ttu-id="d507b-149">모든 이름을 작은따옴표 내에 포함시킵니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-149">Includes all names in single quotes.</span></span>|
|<span data-ttu-id="d507b-150">**/raweh**</span><span class="sxs-lookup"><span data-stu-id="d507b-150">**/raweh**</span></span>|<span data-ttu-id="d507b-151">예외 처리 절을 원시 형식으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-151">Shows exception handling clauses in raw form.</span></span>|
|<span data-ttu-id="d507b-152">**/source**</span><span class="sxs-lookup"><span data-stu-id="d507b-152">**/source**</span></span>|<span data-ttu-id="d507b-153">주석에 따라 원본 소스 줄을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-153">Shows original source lines as comments.</span></span>|
|<span data-ttu-id="d507b-154">**/tokens**</span><span class="sxs-lookup"><span data-stu-id="d507b-154">**/tokens**</span></span>|<span data-ttu-id="d507b-155">클래스 및 멤버의 메타데이터 토큰을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-155">Shows metadata tokens of classes and members.</span></span>|
|<span data-ttu-id="d507b-156">**/visibility:** `vis`[+`vis`...]</span><span class="sxs-lookup"><span data-stu-id="d507b-156">**/visibility:** `vis`[+`vis`...]</span></span>|<span data-ttu-id="d507b-157">지정된 표시 범위의 형식 또는 멤버만 디스어셈블합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-157">Disassembles only types or members with the specified visibility.</span></span> <span data-ttu-id="d507b-158">다음은 `vis`에 사용할 수 있는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-158">The following are valid values for `vis`:</span></span><br /><br /> <span data-ttu-id="d507b-159">**PUB** - Public</span><span class="sxs-lookup"><span data-stu-id="d507b-159">**PUB** — Public</span></span><br /><br /> <span data-ttu-id="d507b-160">**PRI** - Private</span><span class="sxs-lookup"><span data-stu-id="d507b-160">**PRI** — Private</span></span><br /><br /> <span data-ttu-id="d507b-161">**FAM** - Family</span><span class="sxs-lookup"><span data-stu-id="d507b-161">**FAM** — Family</span></span><br /><br /> <span data-ttu-id="d507b-162">**ASM** - Assembly</span><span class="sxs-lookup"><span data-stu-id="d507b-162">**ASM** — Assembly</span></span><br /><br /> <span data-ttu-id="d507b-163">**FAA** - Family and Assembly</span><span class="sxs-lookup"><span data-stu-id="d507b-163">**FAA** — Family and Assembly</span></span><br /><br /> <span data-ttu-id="d507b-164">**FOA** - Family or Assembly</span><span class="sxs-lookup"><span data-stu-id="d507b-164">**FOA** — Family or Assembly</span></span><br /><br /> <span data-ttu-id="d507b-165">**PSC** - Private Scope</span><span class="sxs-lookup"><span data-stu-id="d507b-165">**PSC** — Private Scope</span></span><br /><br /> <span data-ttu-id="d507b-166">이러한 표시 한정자의 정의는 <xref:System.Reflection.MethodAttributes> 및 <xref:System.Reflection.TypeAttributes>를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d507b-166">For definitions of these visibility modifiers, see <xref:System.Reflection.MethodAttributes> and <xref:System.Reflection.TypeAttributes>.</span></span>|

<span data-ttu-id="d507b-167">*.exe*, *.dll* 및 *.winmd* 파일에 대해 파일 또는 콘솔 출력 전용으로 사용할 수 있는 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-167">The following options are valid for *.exe*, *.dll*, and *.winmd* files for file or console output only.</span></span>

| <span data-ttu-id="d507b-168">옵션</span><span class="sxs-lookup"><span data-stu-id="d507b-168">Option</span></span> | <span data-ttu-id="d507b-169">설명</span><span class="sxs-lookup"><span data-stu-id="d507b-169">Description</span></span> |
| ------ | ----------- |
|<span data-ttu-id="d507b-170">**/all**</span><span class="sxs-lookup"><span data-stu-id="d507b-170">**/all**</span></span>|<span data-ttu-id="d507b-171">**/header**, **/bytes**, **/stats**, **/classlist**, **/tokens** 옵션 조합을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-171">Specifies a combination of the **/header**, **/bytes**, **/stats**, **/classlist**, and **/tokens** options.</span></span>|
|<span data-ttu-id="d507b-172">**/classlist**</span><span class="sxs-lookup"><span data-stu-id="d507b-172">**/classlist**</span></span>|<span data-ttu-id="d507b-173">모듈에 정의된 클래스 목록을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-173">Includes a list of classes defined in the module.</span></span>|
|<span data-ttu-id="d507b-174">**/forward**</span><span class="sxs-lookup"><span data-stu-id="d507b-174">**/forward**</span></span>|<span data-ttu-id="d507b-175">정방향 클래스 선언을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-175">Uses forward class declaration.</span></span>|
|<span data-ttu-id="d507b-176">**/headers**</span><span class="sxs-lookup"><span data-stu-id="d507b-176">**/headers**</span></span>|<span data-ttu-id="d507b-177">출력에 파일 헤더 정보를 포함시킵니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-177">Includes file header information in the output.</span></span>|
|<span data-ttu-id="d507b-178">**/item:** `class`[ **::** `member`[`(sig`]]</span><span class="sxs-lookup"><span data-stu-id="d507b-178">**/item:** `class`[**::** `member`[`(sig`]]</span></span>|<span data-ttu-id="d507b-179">지정된 인수에 따라 다음과 같이 디스어셈블합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-179">Disassembles the following depending upon the argument supplied:</span></span><br /><br /> <span data-ttu-id="d507b-180">-   지정된 `class`를 디스어셈블합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-180">-   Disassembles the specified `class`.</span></span><br /><span data-ttu-id="d507b-181">-   지정된 `class`의 `member`를 디스어셈블합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-181">-   Disassembles the specified `member` of the `class`.</span></span><br /><span data-ttu-id="d507b-182">-   지정된 시그니처 `sig`가 포함된 `class`의 `member`를 디스어셈블합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-182">-   Disassembles the `member` of the `class` with the specified signature `sig`.</span></span> <span data-ttu-id="d507b-183">`sig` 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-183">The format of `sig` is:</span></span><br />     <span data-ttu-id="d507b-184">[`instance`] `returnType`(`parameterType1`, `parameterType2`, …, `parameterTypeN`)</span><span class="sxs-lookup"><span data-stu-id="d507b-184">[`instance`] `returnType`(`parameterType1`, `parameterType2`, …, `parameterTypeN`)</span></span><br />     <span data-ttu-id="d507b-185">**참고** .NET Framework 버전 1.0 및 1.1에서는 `(sig)`와 같이 `sig` 다음에 닫는 괄호가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-185">**Note** In the .NET Framework versions 1.0 and 1.1, `sig` must be followed by a closing parenthesis: `(sig)`.</span></span> <span data-ttu-id="d507b-186">.Net Framework 2.0부터는 `(sig`와 같이 닫는 괄호를 생략해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-186">Starting with the Net Framework 2.0 the closing parenthesis must be omitted: `(sig`.</span></span>|
|<span data-ttu-id="d507b-187">**/noil**</span><span class="sxs-lookup"><span data-stu-id="d507b-187">**/noil**</span></span>|<span data-ttu-id="d507b-188">IL 어셈블리 코드 출력을 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-188">Suppresses IL assembly code output.</span></span>|
|<span data-ttu-id="d507b-189">**/stats**</span><span class="sxs-lookup"><span data-stu-id="d507b-189">**/stats**</span></span>|<span data-ttu-id="d507b-190">이미지에 대한 통계를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-190">Includes statistics on the image.</span></span>|
|<span data-ttu-id="d507b-191">**/typelist**</span><span class="sxs-lookup"><span data-stu-id="d507b-191">**/typelist**</span></span>|<span data-ttu-id="d507b-192">라운드트립에서 형식 순서를 유지하기 위해 전체 형식 목록을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-192">Produces the full list of types, to preserve type ordering in a round trip.</span></span>|
|<span data-ttu-id="d507b-193">**/unicode**</span><span class="sxs-lookup"><span data-stu-id="d507b-193">**/unicode**</span></span>|<span data-ttu-id="d507b-194">출력에 유니코드 인코딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-194">Uses Unicode encoding for the output.</span></span>|
|<span data-ttu-id="d507b-195">**/utf8**</span><span class="sxs-lookup"><span data-stu-id="d507b-195">**/utf8**</span></span>|<span data-ttu-id="d507b-196">출력에 UTF-8 인코딩을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-196">Uses UTF-8 encoding for the output.</span></span> <span data-ttu-id="d507b-197">ANSI가 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-197">ANSI is the default.</span></span>|

<span data-ttu-id="d507b-198">*.exe*, *.dll*, *.obj*, *.lib* 및 *.winmd* 파일에 대해 파일 또는 콘솔 출력 전용으로 사용할 수 있는 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-198">The following options are valid for *.exe*, *.dll*, *.obj*, *.lib*, and *.winmd* files for file or console output only.</span></span>

| <span data-ttu-id="d507b-199">옵션</span><span class="sxs-lookup"><span data-stu-id="d507b-199">Option</span></span> | <span data-ttu-id="d507b-200">설명</span><span class="sxs-lookup"><span data-stu-id="d507b-200">Description</span></span> |
| ------ | ----------- |
|<span data-ttu-id="d507b-201">**/metadata**[=`specifier`]</span><span class="sxs-lookup"><span data-stu-id="d507b-201">**/metadata**[=`specifier`]</span></span>|<span data-ttu-id="d507b-202">메타데이터를 표시합니다. `specifier`는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-202">Shows metadata, where `specifier` is:</span></span><br /><br /> <span data-ttu-id="d507b-203">**MDHEADER** - 메타데이터 헤더 정보 및 크기를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-203">**MDHEADER** — Show the metadata header information and sizes.</span></span><br /><br /> <span data-ttu-id="d507b-204">**HEX** - 정보를 단어뿐만 아니라 16진수로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-204">**HEX** — Show information in hex as well as in words.</span></span><br /><br /> <span data-ttu-id="d507b-205">**CSV** - 레코드 개수 및 힙 크기를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-205">**CSV** — Show the record counts and heap sizes.</span></span><br /><br /> <span data-ttu-id="d507b-206">**UNREX** - 확인할 수 없는 외부 참조를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-206">**UNREX** — Show unresolved externals.</span></span><br /><br /> <span data-ttu-id="d507b-207">**SCHEMA** - 메타데이터 헤더 및 스키마 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-207">**SCHEMA** — Show the metadata header and schema information.</span></span><br /><br /> <span data-ttu-id="d507b-208">**RAW** - 원시 메타데이터 테이블을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-208">**RAW** — Show the raw metadata tables.</span></span><br /><br /> <span data-ttu-id="d507b-209">**HEAPS** - 원시 힙을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-209">**HEAPS** — Show the raw heaps.</span></span><br /><br /> <span data-ttu-id="d507b-210">**VALIDATE** - 메타데이터의 일관성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-210">**VALIDATE** — Validate the consistency of the metadata.</span></span><br /><br /> <span data-ttu-id="d507b-211">`specifier`에 대해 다른 값을 사용하여 **/metadata**를 여러 번 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-211">You can specify **/metadata** multiple times, with different values for `specifier`.</span></span>|

<span data-ttu-id="d507b-212">*.lib* 파일에 대해 파일 또는 콘솔 출력 전용으로 사용할 수 있는 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-212">The following options are valid for *.lib* files for file or console output only.</span></span>

| <span data-ttu-id="d507b-213">옵션</span><span class="sxs-lookup"><span data-stu-id="d507b-213">Option</span></span> | <span data-ttu-id="d507b-214">설명</span><span class="sxs-lookup"><span data-stu-id="d507b-214">Description</span></span> |
| ------ | ----------- |
|<span data-ttu-id="d507b-215">**/objectfile**=`filename`</span><span class="sxs-lookup"><span data-stu-id="d507b-215">**/objectfile**=`filename`</span></span>|<span data-ttu-id="d507b-216">지정된 라이브러리에 있는 단일 개체 파일의 메타데이터를 표시합니다</span><span class="sxs-lookup"><span data-stu-id="d507b-216">Shows the metadata of a single object file in the specified library.</span></span>|

> [!NOTE]
> <span data-ttu-id="d507b-217">*Ildasm.exe*의 모든 옵션은 대/소문자가 구분되지 않으며 처음 세 문자로 인식됩니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-217">All options for *Ildasm.exe* are case-insensitive and recognized by the first three letters.</span></span> <span data-ttu-id="d507b-218">예를 들어 **/quo**는 **/quoteallnames**와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-218">For example, **/quo** is equivalent to **/quoteallnames**.</span></span> <span data-ttu-id="d507b-219">인수를 지정하는 옵션에는 옵션과 인수 사이의 구분 기호로 콜론(:) 또는 등호(=) 중 하나만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-219">Options that specify arguments accept either a colon (:) or an equal sign (=) as the separator between the option and the argument.</span></span> <span data-ttu-id="d507b-220">예를 들어 **/output:** *filename*은 **/output=** *filename*과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-220">For example, **/output:** *filename* is equivalent to **/output=** *filename*.</span></span>

## <a name="remarks"></a><span data-ttu-id="d507b-221">설명</span><span class="sxs-lookup"><span data-stu-id="d507b-221">Remarks</span></span>

<span data-ttu-id="d507b-222">*Ildasm.exe*는 디스크의 PE 파일에 대해서만 작동하며,</span><span class="sxs-lookup"><span data-stu-id="d507b-222">*Ildasm.exe* only operates on PE files on disk.</span></span> <span data-ttu-id="d507b-223">전역 어셈블리 캐시에 설치된 파일에 대해서는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-223">It does not operate on files installed in the global assembly cache.</span></span>

<span data-ttu-id="d507b-224">*Ildasm.exe*를 사용하여 생성한 텍스트 파일은 IL 어셈블러(*Ilasm.exe*)에 대한 입력 파일로 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-224">The text file produced by *Ildasm.exe* can be used as input to the IL Assembler (*Ilasm.exe*).</span></span> <span data-ttu-id="d507b-225">이렇게 하면 런타임 메타데이터 특성을 모두 지원하지 않는 프로그래밍 언어로 코드를 컴파일할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-225">This is useful, for example, when compiling code in a programming language that does not support all the runtime metadata attributes.</span></span> <span data-ttu-id="d507b-226">코드를 컴파일하고 *Ildasm.exe*를 사용하여 출력을 실행한 후에는 결과로 만들어지는 IL 텍스트 파일을 수동으로 편집하여 손실된 특성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-226">After compiling the code and running its output through *Ildasm.exe*, the resulting IL text file can be hand-edited to add the missing attributes.</span></span> <span data-ttu-id="d507b-227">그런 다음에는 IL 어셈블러를 통해 이 텍스트 파일을 실행하여 최종 실행 파일을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-227">You can then run this text file through the IL Assembler to produce a final executable file.</span></span>

> [!NOTE]
> <span data-ttu-id="d507b-228">포함된 네이티브 코드가 들어 있는 PE 파일(예: Visual C++로 생성된 PE 파일)에는 현재 이 방법을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-228">Currently, you cannot use this technique with PE files that contain embedded native code (for example, PE files produced by Visual C++).</span></span>  

<span data-ttu-id="d507b-229">IL 디스어셈블러의 기본 GUI를 사용하면 계층 구조 트리 뷰에서 기존 PE 파일의 메타데이터 및 디스어셈블된 코드를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-229">You can use the default GUI in the IL Disassembler to view the metadata and disassembled code of any existing PE file in a hierarchical tree view.</span></span> <span data-ttu-id="d507b-230">이 GUI를 사용하려면 해당 명령줄에서 **ildasm**을 입력합니다. 이때 *PEfilename* 인수나 기타 옵션은 지정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-230">To use the GUI, type **ildasm** at the command line without supplying the *PEfilename* argument or any options.</span></span> <span data-ttu-id="d507b-231">**파일** 메뉴에서 *Ildasm.exe*에 로드하려는 PE 파일 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-231">From the **File** menu, you can navigate to the PE file that you want to load into *Ildasm.exe*.</span></span> <span data-ttu-id="d507b-232">선택한 PE에 대해 표시된 메타데이터 및 디스어셈블된 코드를 저장하려면 **파일** 메뉴에서 **덤프** 명령을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-232">To save the metadata and disassembled code displayed for the selected PE, select the **Dump** command from the **File** menu.</span></span> <span data-ttu-id="d507b-233">계층 구조 트리 뷰만 저장하려면 **파일** 메뉴에서 **트리 뷰 덤프** 명령을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-233">To save the hierarchical tree view only, select the **Dump Treeview** command from the **File** menu.</span></span> <span data-ttu-id="d507b-234">*Ildasm.exe*로 파일을 로드하고 출력 내용을 해석하는 방법에 대한 자세한 지침을 보려면 Windows SDK와 함께 제공되는 Samples 폴더의 *Ildasm.exe* 자습서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d507b-234">For a detailed guide to loading a file into *Ildasm.exe* and interpreting the output, see the *Ildasm.exe* Tutorial, located in the Samples folder that ships with the Windows SDK.</span></span>

<span data-ttu-id="d507b-235">*Ildasm.exe*에 포함 리소스가 들어 있는 *PEfilename* 인수를 제공하면 여러 개의 출력 파일이 생성됩니다. 즉, IL 코드가 들어 있는 텍스트 파일이 생성되고, 관리되는 각 포함 리소스의 경우 메타데이터의 리소스 이름을 사용하여 .resources 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-235">If you provide *Ildasm.exe* with a *PEfilename* argument that contains embedded resources, the tool produces multiple output files: a text file that contains IL code and, for each embedded managed resource, a .resources file produced using the resource's name from metadata.</span></span> <span data-ttu-id="d507b-236">관리되지 않는 리소스가 *PEfilename*에 포함되어 있으면 **/output** 옵션으로 IL 출력에 대해 지정한 파일 이름을 사용하여 .res 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-236">If an unmanaged resource is embedded in *PEfilename*, a .res file is produced using the filename specified for IL output by the **/output** option.</span></span>

> [!NOTE]
> <span data-ttu-id="d507b-237">*Ildasm.exe*를 사용하면 *.obj* 및 *.lib* 입력 파일에 대해 메타데이터 설명만 표시되며,</span><span class="sxs-lookup"><span data-stu-id="d507b-237">*Ildasm.exe* shows only metadata descriptions for *.obj* and *.lib* input files.</span></span> <span data-ttu-id="d507b-238">이러한 파일 형식에 대한 IL 코드는 디스어셈블되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-238">IL code for these file types is not disassembled.</span></span>

<span data-ttu-id="d507b-239">.exe 또는 *.dll* 파일을 통해 *Ildasm.exe*를 실행하여 파일이 관리되는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-239">You can run *Ildasm.exe* over an.exe or *.dll* file to determine whether the file is managed.</span></span> <span data-ttu-id="d507b-240">파일이 관리되지 않으면 파일에 올바른 공용 언어 런타임 헤더가 없어 디스어셈블될 수 없음을 나타내는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-240">If the file is not managed, the tool displays a message stating that the file has no valid common language runtime header and cannot be disassembled.</span></span> <span data-ttu-id="d507b-241">파일이 관리되면 도구가 성공적으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-241">If the file is managed, the tool runs successfully.</span></span>

## <a name="version-information"></a><span data-ttu-id="d507b-242">버전 정보</span><span class="sxs-lookup"><span data-stu-id="d507b-242">Version Information</span></span>

<span data-ttu-id="d507b-243">.NET Framework 4.5부터 제공되는 *Ildasm.exe*는 원시 이진 콘텐츠를 표시하여 인식할 수 없는 마샬 BLOB(Binary Large Object)을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-243">Starting with the .NET Framework 4.5, *Ildasm.exe* handles an unrecognized marshal BLOB (binary large object) by displaying the raw binary content.</span></span> <span data-ttu-id="d507b-244">예를 들어, 다음 코드는 C# 프로그램에서 생성된 마샬 BLOB가 표시되는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-244">For example, the following code shows how a marshal BLOB generated by a C# program is displayed:</span></span>

```csharp
public void Test([MarshalAs((short)70)] int test) { }
```

```il
// IL from Ildasm.exe output
.method public hidebysig instance void Test(int32  marshal({ 46 }) test) cil managed
```

<span data-ttu-id="d507b-245">.NET Framework 4.5부터 제공되는 *Ildasm.exe*는 *Ildasm.exe* 출력에서 발췌한 다음 예제에서와 같이 인터페이스 구현에 적용되는 특성을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-245">Starting with the .NET Framework 4.5, *Ildasm.exe* displays attributes that are applied to interface implementations, as shown in the following excerpt from *Ildasm.exe* output:</span></span>

```il
.class public auto ansi beforefieldinit MyClass
  extends [mscorlib]System.Object
  implements IMyInterface
  {
    .interfaceimpl type IMyInterface
    .custom instance void
      [mscorlib]System.Diagnostics.DebuggerNonUserCodeAttribute::.ctor() = ( 01 00 00 00 )
      …
```

## <a name="examples"></a><span data-ttu-id="d507b-246">예</span><span class="sxs-lookup"><span data-stu-id="d507b-246">Examples</span></span>

<span data-ttu-id="d507b-247">다음 명령을 사용하여 PE 파일 `MyHello.exe`에 대한 메타데이터 및 디스어셈블된 코드를 *Ildasm.exe*의 기본 GUI에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-247">The following command causes the metadata and disassembled code for the PE file `MyHello.exe` to display in the *Ildasm.exe* default GUI.</span></span>

```console
ildasm myHello.exe
```

<span data-ttu-id="d507b-248">다음 명령을 사용하여 `MyFile.exe` 파일을 디스어셈블하고 그 결과로 만들어지는 IL 어셈블러 텍스트를 *MyFile.il* 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-248">The following command disassembles the file `MyFile.exe` and stores the resulting IL Assembler text in the file *MyFile.il*.</span></span>

```console
ildasm MyFile.exe /output:MyFile.il
```

<span data-ttu-id="d507b-249">다음 명령을 사용하여 `MyFile.exe` 파일을 디스어셈블하고 그 결과로 만들어지는 IL 어셈블러 텍스트를 콘솔 창에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-249">The following command disassembles the file `MyFile.exe` and displays the resulting IL Assembler text to the console window.</span></span>

```console
ildasm MyFile.exe /text
```

<span data-ttu-id="d507b-250">`MyApp.exe` 파일에 관리되는 포함 리소스와 관리되지 않은 포함 리소스가 들어 있는 경우 다음 명령을 사용하여 *MyApp.il*, *MyApp.res*, *Icons.resources*, *Message.resources* 등 네 개의 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-250">If the file `MyApp.exe` contains embedded managed and unmanaged resources, the following command produces four files: *MyApp.il*, *MyApp.res*, *Icons.resources*, and *Message.resources*:</span></span>

```console
ildasm MyApp.exe /output:MyApp.il
```

<span data-ttu-id="d507b-251">다음 명령을 사용하여 `MyFile.exe`의 `MyClass` 클래스 내에 있는 `MyMethod` 메서드를 디스어셈블하고 해당 출력을 콘솔 창에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-251">The following command disassembles the method `MyMethod` within the class `MyClass` in `MyFile.exe` and displays the output to the console window.</span></span>

```console
ildasm /item:MyClass::MyMethod MyFile.exe /text
```

<span data-ttu-id="d507b-252">앞의 예제에서는 시그니처가 서로 다른 `MyMethod` 메서드가 여러 개 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-252">In the previous example, there could be several methods named `MyMethod` with different signatures.</span></span> <span data-ttu-id="d507b-253">다음 명령을 사용하여 반환 형식이 **void**이고 매개 변수 형식이 **int32** 및 **string**인 인스턴스 메서드 `MyMethod`를 디스어셈블합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-253">The following command disassembles the instance method `MyMethod` with the return type of **void** and the parameter types **int32** and **string**.</span></span>

```console
ildasm /item:"MyClass::MyMethod(instance void(int32,string)" MyFile.exe /text
```

> [!NOTE]
> <span data-ttu-id="d507b-254">.NET Framework 버전 1.0 및 1.1에서는 `MyMethod(instance void(int32))`와 같이 메서드 이름 다음의 왼쪽 괄호와 시그니처 다음의 오른쪽 괄호가 짝을 이뤄야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-254">In the .NET Framework versions 1.0 and 1.1, the left parenthesis that follows the method name must be balanced by a right parenthesis after the signature: `MyMethod(instance void(int32))`.</span></span> <span data-ttu-id="d507b-255">.NET Framework 2.0부터는 `MyMethod(instance void(int32)`와 같이 닫는 괄호를 생략해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-255">Starting with the .NET Framework 2.0 the closing parenthesis must be omitted: `MyMethod(instance void(int32)`.</span></span>

<span data-ttu-id="d507b-256">`static` 메서드(Visual Basic의 경우 `Shared` 메서드)를 검색하려면 `instance` 키워드를 생략합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-256">To retrieve a `static` method (`Shared` method in Visual Basic), omit the keyword `instance`.</span></span> <span data-ttu-id="d507b-257">`int32` 및 `string`과 같이 기본 형식이 아닌 클래스 형식은 네임스페이스를 포함해야 하며 앞에 `class` 키워드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-257">Class types that are not primitive types like `int32` and `string` must include the namespace and must be preceded by the keyword `class`.</span></span> <span data-ttu-id="d507b-258">외부 형식 앞에는 대괄호로 묶인 라이브러리 이름이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-258">External types must be preceded by the library name in square brackets.</span></span> <span data-ttu-id="d507b-259">다음 명령은 `MyMethod` 형식의 매개 변수가 하나 있고 반환 형식이 <xref:System.AppDomain>인 <xref:System.AppDomain>라는 정적 메서드를 디스어셈블합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-259">The following command disassembles a static method named `MyMethod` that has one parameter of type <xref:System.AppDomain> and has a return type of <xref:System.AppDomain>.</span></span>

```console
ildasm /item:"MyClass::MyMethod(class [mscorlib]System.AppDomain(class [mscorlib]System.AppDomain)" MyFile.exe /text
```

<span data-ttu-id="d507b-260">중첩 형식은 해당 형식을 포함하는 클래스와 슬래시 다음에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-260">A nested type must be preceded by its containing class, delimited by a forward slash.</span></span> <span data-ttu-id="d507b-261">예를 들어, `MyNamespace.MyClass` 클래스에 `NestedClass`라는 중첩 클래스가 들어 있으면 중첩 클래스는 `class MyNamespace.MyClass/NestedClass`로 식별됩니다.</span><span class="sxs-lookup"><span data-stu-id="d507b-261">For example, if the `MyNamespace.MyClass` class contains a nested class named `NestedClass`, the nested class is identified as follows: `class MyNamespace.MyClass/NestedClass`.</span></span>

## <a name="see-also"></a><span data-ttu-id="d507b-262">참조</span><span class="sxs-lookup"><span data-stu-id="d507b-262">See also</span></span>

- [<span data-ttu-id="d507b-263">도구</span><span class="sxs-lookup"><span data-stu-id="d507b-263">Tools</span></span>](index.md)
- [<span data-ttu-id="d507b-264">Ilasm.exe(IL 어셈블러)</span><span class="sxs-lookup"><span data-stu-id="d507b-264">Ilasm.exe (IL Assembler)</span></span>](ilasm-exe-il-assembler.md)
- [<span data-ttu-id="d507b-265">관리되는 실행 프로세스</span><span class="sxs-lookup"><span data-stu-id="d507b-265">Managed Execution Process</span></span>](../../standard/managed-execution-process.md)
- [<span data-ttu-id="d507b-266">명령 프롬프트</span><span class="sxs-lookup"><span data-stu-id="d507b-266">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
