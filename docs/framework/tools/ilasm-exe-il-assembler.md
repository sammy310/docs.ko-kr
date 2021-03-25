---
title: Ilasm.exe(IL 어셈블러)
description: Ilasm.exe 즉, IL 어셈블러를 시작합니다. 이 도구는 IL(중간 언어) 어셈블리에서 PE(이식 가능한 실행) 파일을 생성합니다.
ms.date: 03/30/2017
helpviewer_keywords:
- MSIL generators
- metadata, MSIL Assembler
- MSIL Assembler
- portable executable files, MSIL Assembler
- PE files, MSIL Assembler
- MSIL
- Ilasm.exe
- verifying MSIL performance
ms.assetid: 4ca3a4f0-4400-47ce-8936-8e219961c76f
ms.openlocfilehash: 6057c8dcaaa8a8f8873e5807009e1b0422f4ff33
ms.sourcegitcommit: 1dbe25ff484a02025d5c34146e517c236f7161fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "104654130"
---
# <a name="ilasmexe-il-assembler"></a><span data-ttu-id="0aca0-104">Ilasm.exe(IL 어셈블러)</span><span class="sxs-lookup"><span data-stu-id="0aca0-104">Ilasm.exe (IL Assembler)</span></span>

<span data-ttu-id="0aca0-105">IL 어셈블러는 IL(중간 언어) 어셈블리에서 PE(이식 가능한 실행) 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-105">The IL Assembler generates a portable executable (PE) file from intermediate language (IL) assembly.</span></span> <span data-ttu-id="0aca0-106">IL에 대한 자세한 내용은 [관리되는 실행 프로세스](../../standard/managed-execution-process.md)를 참조하세요. 이렇게 생성된 실행 파일에는 IL 및 필요한 메타데이터가 들어 있으며, 이 파일을 실행하면 IL이 예상대로 실행되는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-106">(For more information on IL, see [Managed Execution Process](../../standard/managed-execution-process.md).) You can run the resulting executable, which contains IL and the required metadata, to determine whether the IL performs as expected.</span></span>

<span data-ttu-id="0aca0-107">이 도구는 자동으로 Visual Studio와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-107">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="0aca0-108">도구를 실행하려면 [Visual Studio 개발자 명령 프롬프트 또는 Visual Studio 개발자 PowerShell](/visualstudio/ide/reference/command-prompt-powershell)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-108">To run the tool, use [Visual Studio Developer Command Prompt or Visual Studio Developer PowerShell](/visualstudio/ide/reference/command-prompt-powershell).</span></span>

<span data-ttu-id="0aca0-109">명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-109">At the command prompt, type the following:</span></span>

## <a name="syntax"></a><span data-ttu-id="0aca0-110">구문</span><span class="sxs-lookup"><span data-stu-id="0aca0-110">Syntax</span></span>

```console
ilasm [options] filename [[options]filename...]
```

## <a name="parameters"></a><span data-ttu-id="0aca0-111">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0aca0-111">Parameters</span></span>

| <span data-ttu-id="0aca0-112">인수</span><span class="sxs-lookup"><span data-stu-id="0aca0-112">Argument</span></span> | <span data-ttu-id="0aca0-113">Description</span><span class="sxs-lookup"><span data-stu-id="0aca0-113">Description</span></span> |
| -------- | ----------- |
|`filename`|<span data-ttu-id="0aca0-114">.il 소스 파일의 이름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-114">The name of the .il source file.</span></span> <span data-ttu-id="0aca0-115">이 파일은 메타데이터 선언 지시문과 기호화된 IL 명령으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-115">This file consists of metadata declaration directives and symbolic IL instructions.</span></span> <span data-ttu-id="0aca0-116">*Ilasm.exe* 를 사용하여 여러 개의 소스 파일 인수를 제공하면 하나의 PE 파일을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-116">Multiple source file arguments can be supplied to produce a single PE file with *Ilasm.exe*.</span></span> <span data-ttu-id="0aca0-117">**참고:** .il 소스 파일의 마지막 코드 줄에는 후행 공백이나 줄 끝(EOL) 문자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-117">**Note:** Ensure that the last line of code in the .il source file has either trailing white space or an end-of-line character.</span></span>|

| <span data-ttu-id="0aca0-118">옵션</span><span class="sxs-lookup"><span data-stu-id="0aca0-118">Option</span></span> | <span data-ttu-id="0aca0-119">설명</span><span class="sxs-lookup"><span data-stu-id="0aca0-119">Description</span></span> |
| ------ | ----------- |
|<span data-ttu-id="0aca0-120">**/32bitpreferred**</span><span class="sxs-lookup"><span data-stu-id="0aca0-120">**/32bitpreferred**</span></span>|<span data-ttu-id="0aca0-121">32비트 우선의 이미지(PE32)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-121">Creates a 32-bit-preferred image (PE32).</span></span>|
|<span data-ttu-id="0aca0-122">**/alignment:** `integer`</span><span class="sxs-lookup"><span data-stu-id="0aca0-122">**/alignment:** `integer`</span></span>|<span data-ttu-id="0aca0-123">FileAlignment를 NT 선택적 헤더의 `integer`에서 지정한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-123">Sets FileAlignment to the value specified by `integer` in the NT Optional header.</span></span> <span data-ttu-id="0aca0-124">.alignment IL 지시문이 파일에 지정된 경우 이 옵션을 사용하면 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-124">If the .alignment IL directive is specified in the file, this option overrides it.</span></span>|
|<span data-ttu-id="0aca0-125">**/appcontainer**</span><span class="sxs-lookup"><span data-stu-id="0aca0-125">**/appcontainer**</span></span>|<span data-ttu-id="0aca0-126">Windows 앱 컨테이너에서 출력으로 실행되는 *.dll* 또는 *.exe* 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-126">Produces a *.dll* or *.exe* file that runs in the Windows app container, as output.</span></span>|
|<span data-ttu-id="0aca0-127">**/arm**</span><span class="sxs-lookup"><span data-stu-id="0aca0-127">**/arm**</span></span>|<span data-ttu-id="0aca0-128">Advanced RISC Machine(ARM)을 대상 프로세서로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-128">Specifies the Advanced RISC Machine (ARM) as the target processor.</span></span><br /><br /> <span data-ttu-id="0aca0-129">이미지 비트가 지정되지 않은 경우 기본값은 **/32bitpreferred** 입니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-129">If no image bitness is specified, the default is **/32bitpreferred**.</span></span>|
|<span data-ttu-id="0aca0-130">**/base:** `integer`</span><span class="sxs-lookup"><span data-stu-id="0aca0-130">**/base:** `integer`</span></span>|<span data-ttu-id="0aca0-131">ImageBase를 NT 선택적 헤더의 `integer`에서 지정한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-131">Sets ImageBase to the value specified by `integer` in the NT Optional header.</span></span> <span data-ttu-id="0aca0-132">.imagebase IL 지시문이 파일에 지정된 경우 이 옵션을 사용하면 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-132">If the .imagebase IL directive is specified in the file, this option overrides it.</span></span>|
|<span data-ttu-id="0aca0-133">**/clock**</span><span class="sxs-lookup"><span data-stu-id="0aca0-133">**/clock**</span></span>|<span data-ttu-id="0aca0-134">지정된 .il 소스 파일에 대해 다음 컴파일 타임을 밀리초 단위로 측정하여 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-134">Measures and reports the following compilation times in milliseconds for the specified .il source file:</span></span><br /><br /> <span data-ttu-id="0aca0-135">**Total Run**: 다음의 특정 작업을 모두 수행하는 데 걸린 총 시간.</span><span class="sxs-lookup"><span data-stu-id="0aca0-135">**Total Run**: The total time spent performing all the specific operations that follow.</span></span><br /><br /> <span data-ttu-id="0aca0-136">**Startup**: 파일 로드 및 열기.</span><span class="sxs-lookup"><span data-stu-id="0aca0-136">**Startup**: Loading and opening the file.</span></span><br /><br /> <span data-ttu-id="0aca0-137">**Emitting MD**: 메타데이터 내보내기.</span><span class="sxs-lookup"><span data-stu-id="0aca0-137">**Emitting MD**: Emitting metadata.</span></span><br /><br /> <span data-ttu-id="0aca0-138">**Ref to Def Resolution**: 파일의 참조를 정의로 확인.</span><span class="sxs-lookup"><span data-stu-id="0aca0-138">**Ref to Def Resolution**: Resolving references to definitions in the file.</span></span><br /><br /> <span data-ttu-id="0aca0-139">**CEE File Generation**: 메모리에 파일 이미지 생성.</span><span class="sxs-lookup"><span data-stu-id="0aca0-139">**CEE File Generation**: Generating the file image in memory.</span></span><br /><br /> <span data-ttu-id="0aca0-140">**PE File Writing**: PE 파일에 이미지 작성.</span><span class="sxs-lookup"><span data-stu-id="0aca0-140">**PE File Writing**: Writing the image to a PE file.</span></span>|
|<span data-ttu-id="0aca0-141">**/debug**[:**IMPL**&#124;**OPT**]</span><span class="sxs-lookup"><span data-stu-id="0aca0-141">**/debug**[:**IMPL**&#124;**OPT**]</span></span>|<span data-ttu-id="0aca0-142">지역 변수 및 인수 이름과 줄 번호 등의 디버깅 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-142">Includes debug information (local variable and argument names, and line numbers).</span></span> <span data-ttu-id="0aca0-143">PDB 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-143">Creates a PDB file.</span></span><br /><br /> <span data-ttu-id="0aca0-144">**/debug** 에 추가 값을 지정하지 않으면 JIT 최적화를 사용할 수 없고 PDB 파일의 시퀀스 위치를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-144">**/debug** with no additional value disables JIT optimization and uses sequence points from the PDB file.</span></span><br /><br /> <span data-ttu-id="0aca0-145">**IMPL** 은 JIT 최적화를 사용할 수 없도록 하고 암시적 시퀀스 위치를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-145">**IMPL** disables JIT optimization and uses implicit sequence points.</span></span><br /><br /> <span data-ttu-id="0aca0-146">**OPT** 는 JIT 최적화를 사용할 수 있도록 하고 암시적 시퀀스 위치를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-146">**OPT** enables JIT optimization and uses implicit sequence points.</span></span>|
|<span data-ttu-id="0aca0-147">**/dll**</span><span class="sxs-lookup"><span data-stu-id="0aca0-147">**/dll**</span></span>|<span data-ttu-id="0aca0-148">*.dll* 파일을 출력 파일로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-148">Produces a *.dll* file as output.</span></span>|
|<span data-ttu-id="0aca0-149">**/enc:** `file`</span><span class="sxs-lookup"><span data-stu-id="0aca0-149">**/enc:** `file`</span></span>|<span data-ttu-id="0aca0-150">지정한 소스 파일에서 편집하며 계속하기 델타를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-150">Creates Edit-and-Continue deltas from the specified source file.</span></span><br /><br /> <span data-ttu-id="0aca0-151">이 인수는 교육용 버전에서만 사용되며, 상업용 버전에서는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-151">This argument is for academic use only and is not supported for commercial use.</span></span>|
|<span data-ttu-id="0aca0-152">**/exe**</span><span class="sxs-lookup"><span data-stu-id="0aca0-152">**/exe**</span></span>|<span data-ttu-id="0aca0-153">실행 파일을 출력 파일로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-153">Produces an executable file as output.</span></span> <span data-ttu-id="0aca0-154">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-154">This is the default.</span></span>|
|<span data-ttu-id="0aca0-155">**/flags:** `integer`</span><span class="sxs-lookup"><span data-stu-id="0aca0-155">**/flags:** `integer`</span></span>|<span data-ttu-id="0aca0-156">ImageFlags를 공용 언어 런타임 헤더의 `integer`에서 지정한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-156">Sets ImageFlags to the value specified by `integer` in the common language runtime header.</span></span> <span data-ttu-id="0aca0-157">.corflags IL 지시문이 파일에 지정된 경우 이 옵션을 사용하면 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-157">If the .corflags IL directive is specified in the file, this option overrides it.</span></span> <span data-ttu-id="0aca0-158">*integer* 의 올바른 값 목록은 CorHdr.h, COMIMAGE_FLAGS를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="0aca0-158">See CorHdr.h, COMIMAGE_FLAGS for a list of valid values for *integer*.</span></span>|
|<span data-ttu-id="0aca0-159">**/fold**</span><span class="sxs-lookup"><span data-stu-id="0aca0-159">**/fold**</span></span>|<span data-ttu-id="0aca0-160">동일한 메서드 본문을 하나로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-160">Folds identical method bodies into one.</span></span>|
|<span data-ttu-id="0aca0-161">/**highentropyva**</span><span class="sxs-lookup"><span data-stu-id="0aca0-161">/**highentropyva**</span></span>|<span data-ttu-id="0aca0-162">높은 엔트로피 주소 공간 레이아웃 불규칙화(ASLR)가 지원되는 출력 실행 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-162">Produces an output executable that supports high-entropy address space layout randomization (ASLR).</span></span> <span data-ttu-id="0aca0-163">( **/appcontainer** 의 기본값)</span><span class="sxs-lookup"><span data-stu-id="0aca0-163">(Default for **/appcontainer**.)</span></span>|
|<span data-ttu-id="0aca0-164">**/include:** `includePath`</span><span class="sxs-lookup"><span data-stu-id="0aca0-164">**/include:** `includePath`</span></span>|<span data-ttu-id="0aca0-165">`#include`에 포함된 파일을 검색할 경로를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-165">Sets a path to search for files included with `#include`.</span></span>|
|<span data-ttu-id="0aca0-166">**/itanium**</span><span class="sxs-lookup"><span data-stu-id="0aca0-166">**/itanium**</span></span>|<span data-ttu-id="0aca0-167">Intel Itanium을 대상 프로세서로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-167">Specifies Intel Itanium as the target processor.</span></span><br /><br /> <span data-ttu-id="0aca0-168">이미지 비트가 지정되지 않은 경우 기본값은 **/pe64** 입니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-168">If no image bitness is specified, the default is **/pe64**.</span></span>|
|<span data-ttu-id="0aca0-169">**/key:** `keyFile`</span><span class="sxs-lookup"><span data-stu-id="0aca0-169">**/key:** `keyFile`</span></span>|<span data-ttu-id="0aca0-170">`keyFile`에 들어 있는 프라이빗 키를 사용하여 강력한 시그니처가 있는 `filename`을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-170">Compiles `filename` with a strong signature using the private key contained in `keyFile`.</span></span>|
|<span data-ttu-id="0aca0-171">**/key:**  @`keySource`</span><span class="sxs-lookup"><span data-stu-id="0aca0-171">**/key:** @`keySource`</span></span>|<span data-ttu-id="0aca0-172">`keySource`에 생성된 프라이빗 키를 사용하여 강력한 시그니처가 있는 `filename`을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-172">Compiles `filename` with a strong signature using the private key produced at `keySource`.</span></span>|
|<span data-ttu-id="0aca0-173">**/listing**</span><span class="sxs-lookup"><span data-stu-id="0aca0-173">**/listing**</span></span>|<span data-ttu-id="0aca0-174">표준 출력 파일에 대한 목록 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-174">Produces a listing file on the standard output.</span></span> <span data-ttu-id="0aca0-175">이 옵션을 생략하면 목록 파일이 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-175">If you omit this option, no listing file is produced.</span></span><br /><br /> <span data-ttu-id="0aca0-176">이 매개 변수는 .NET Framework 2.0 이상에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-176">This parameter is not supported in the .NET Framework 2.0 or later.</span></span>|
|<span data-ttu-id="0aca0-177">**/mdv:** `versionString`</span><span class="sxs-lookup"><span data-stu-id="0aca0-177">**/mdv:** `versionString`</span></span>|<span data-ttu-id="0aca0-178">메타데이터 버전 문자열을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-178">Sets the metadata version string.</span></span>|
|<span data-ttu-id="0aca0-179">**/msv:** `major`.`minor`</span><span class="sxs-lookup"><span data-stu-id="0aca0-179">**/msv:** `major`.`minor`</span></span>|<span data-ttu-id="0aca0-180">`major` 및 `minor` 가 정수인 메타데이터 스트림 버전을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-180">Sets the metadata stream version, where `major` and `minor` are integers.</span></span>|
|<span data-ttu-id="0aca0-181">**/noautoinherit**</span><span class="sxs-lookup"><span data-stu-id="0aca0-181">**/noautoinherit**</span></span>|<span data-ttu-id="0aca0-182">기준 클래스를 지정하지 않으면 <xref:System.Object> 에서 기본 상속을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-182">Disables default inheritance from <xref:System.Object> when no base class is specified.</span></span>|
|<span data-ttu-id="0aca0-183">**/nocorstub**</span><span class="sxs-lookup"><span data-stu-id="0aca0-183">**/nocorstub**</span></span>|<span data-ttu-id="0aca0-184">CORExeMain 스텁을 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-184">Suppresses generation of the CORExeMain stub.</span></span>|
|<span data-ttu-id="0aca0-185">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="0aca0-185">**/nologo**</span></span>|<span data-ttu-id="0aca0-186">Microsoft 시작 배너를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-186">Suppresses the Microsoft startup banner display.</span></span>|
|<span data-ttu-id="0aca0-187">**/output:** `file.ext`</span><span class="sxs-lookup"><span data-stu-id="0aca0-187">**/output:** `file.ext`</span></span>|<span data-ttu-id="0aca0-188">출력 파일 이름 및 확장명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-188">Specifies the output file name and extension.</span></span> <span data-ttu-id="0aca0-189">기본적으로 출력 파일 이름은 첫 번째 소스 파일의 이름과 같으며,</span><span class="sxs-lookup"><span data-stu-id="0aca0-189">By default, the output file name is the same as the name of the first source file.</span></span> <span data-ttu-id="0aca0-190">기본 확장명은 *.exe* 입니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-190">The default extension is *.exe*.</span></span> <span data-ttu-id="0aca0-191">**/dll** 옵션을 지정하는 경우 기본 확장명은 *.dll* 입니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-191">If you specify the **/dll** option, the default extension is *.dll*.</span></span> <span data-ttu-id="0aca0-192">**참고:** **/output**:myfile.dll을 지정하면 **/dll** 옵션이 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-192">**Note:** Specifying **/output**:myfile.dll does not set the **/dll** option.</span></span> <span data-ttu-id="0aca0-193">**/dll** 을 지정하지 않으면 *myfile.dll* 이라는 실행 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-193">If you do not specify **/dll**, the result will be an executable file named *myfile.dll*.</span></span>|
|<span data-ttu-id="0aca0-194">**/optimize**</span><span class="sxs-lookup"><span data-stu-id="0aca0-194">**/optimize**</span></span>|<span data-ttu-id="0aca0-195">긴 명령을 짧게 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-195">Optimizes long instructions to short.</span></span> <span data-ttu-id="0aca0-196">예를 들면, `br` 를 `br.s`로 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-196">For example, `br` to `br.s`.</span></span>|
|<span data-ttu-id="0aca0-197">**/pe64**</span><span class="sxs-lookup"><span data-stu-id="0aca0-197">**/pe64**</span></span>|<span data-ttu-id="0aca0-198">64비트 이미지(PE32+)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-198">Creates a 64-bit image (PE32+).</span></span><br /><br /> <span data-ttu-id="0aca0-199">대상 프로세서가 지정되지 않은 경우 기본값은 `/itanium`입니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-199">If no target processor is specified, the default is `/itanium`.</span></span>|
|<span data-ttu-id="0aca0-200">**/pdb**</span><span class="sxs-lookup"><span data-stu-id="0aca0-200">**/pdb**</span></span>|<span data-ttu-id="0aca0-201">디버그 정보 추적을 사용하지 않고 PDB 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-201">Creates a PDB file without enabling debug information tracking.</span></span>|
|<span data-ttu-id="0aca0-202">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="0aca0-202">**/quiet**</span></span>|<span data-ttu-id="0aca0-203">자동 모드를 지정하여 어셈블리 진행률을 보고하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-203">Specifies quiet mode; does not report assembly progress.</span></span>|
|<span data-ttu-id="0aca0-204">**/resource:** `file.res`</span><span class="sxs-lookup"><span data-stu-id="0aca0-204">**/resource:** `file.res`</span></span>|<span data-ttu-id="0aca0-205">결과로 만들어지는 *.exe* 또는 *.dll* 파일에 \*.res 형식의 지정된 리소스 파일을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-205">Includes the specified resource file in \*.res format in the resulting *.exe* or *.dll* file.</span></span> <span data-ttu-id="0aca0-206">**/resource** 옵션을 사용하여 .res 파일을 하나만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-206">Only one .res file can be specified with the **/resource** option.</span></span>|
|<span data-ttu-id="0aca0-207">**/ssver:** `int`.`int`</span><span class="sxs-lookup"><span data-stu-id="0aca0-207">**/ssver:** `int`.`int`</span></span>|<span data-ttu-id="0aca0-208">NT 선택적 헤더의 하위 시스템 버전 번호를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-208">Sets the subsystem version number in the NT optional header.</span></span> <span data-ttu-id="0aca0-209">**/appcontainer** 및 **/arm** 의 최소 버전 번호는 6.02입니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-209">For **/appcontainer** and **/arm** the minimum version number is 6.02.</span></span>|
|<span data-ttu-id="0aca0-210">**/stack:** `stackSize`</span><span class="sxs-lookup"><span data-stu-id="0aca0-210">**/stack:** `stackSize`</span></span>|<span data-ttu-id="0aca0-211">NT 선택적 헤더의 SizeOfStackReserve 값을 `stackSize`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-211">Sets the SizeOfStackReserve value in the NT Optional header to `stackSize`.</span></span>|
|<span data-ttu-id="0aca0-212">**/stripreloc**</span><span class="sxs-lookup"><span data-stu-id="0aca0-212">**/stripreloc**</span></span>|<span data-ttu-id="0aca0-213">기준 재배치가 필요하지 않도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-213">Specifies that no base relocations are needed.</span></span>|
|<span data-ttu-id="0aca0-214">**/subsystem:** `integer`</span><span class="sxs-lookup"><span data-stu-id="0aca0-214">**/subsystem:** `integer`</span></span>|<span data-ttu-id="0aca0-215">하위 시스템을 NT 선택적 헤더의 `integer`에서 지정한 값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-215">Sets subsystem to the value specified by `integer` in the NT Optional header.</span></span> <span data-ttu-id="0aca0-216">.subsystem IL 지시문이 파일에 지정된 경우 이 명령을 사용하면 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-216">If the .subsystem IL directive is specified in the file, this command overrides it.</span></span> <span data-ttu-id="0aca0-217">`integer`의 올바른 값 목록은 winnt.h, IMAGE_SUBSYSTEM을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0aca0-217">See winnt.h, IMAGE_SUBSYSTEM for a list of valid values for `integer`.</span></span>|
|<span data-ttu-id="0aca0-218">**/x64**</span><span class="sxs-lookup"><span data-stu-id="0aca0-218">**/x64**</span></span>|<span data-ttu-id="0aca0-219">64비트 AMD 프로세서를 대상 프로세서로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-219">Specifies a 64-bit AMD processor as the target processor.</span></span><br /><br /> <span data-ttu-id="0aca0-220">이미지 비트가 지정되지 않은 경우 기본값은 **/pe64** 입니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-220">If no image bitness is specified, the default is **/pe64**.</span></span>|
|<span data-ttu-id="0aca0-221">**/?**</span><span class="sxs-lookup"><span data-stu-id="0aca0-221">**/?**</span></span>|<span data-ttu-id="0aca0-222">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-222">Displays command syntax and options for the tool.</span></span>|

> [!NOTE]
> <span data-ttu-id="0aca0-223">*Ilasm.exe* 의 모든 옵션은 대/소문자가 구분되지 않으며 처음 세 문자로 인식됩니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-223">All options for *Ilasm.exe* are case-insensitive and recognized by the first three letters.</span></span> <span data-ttu-id="0aca0-224">예를 들어 **/lis** 는 **/listing** 과 같고, **/res:** myresfile.res는 **/resource:** myresfile.res와 같습니다. 인수를 지정하는 옵션에는 옵션과 인수 사이의 구분 기호로 콜론(:) 또는 등호(=) 중 하나만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-224">For example, **/lis** is equivalent to **/listing** and **/res**:myresfile.res is equivalent to **/resource**:myresfile.res. Options that specify arguments accept either a colon (:) or an equal sign (=) as the separator between the option and the argument.</span></span> <span data-ttu-id="0aca0-225">예를 들어, **/output**:*file.ext* 는 **/output**=*file.ext* 와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-225">For example, **/output**:*file.ext* is equivalent to **/output**=*file.ext*.</span></span>

## <a name="remarks"></a><span data-ttu-id="0aca0-226">설명</span><span class="sxs-lookup"><span data-stu-id="0aca0-226">Remarks</span></span>

<span data-ttu-id="0aca0-227">IL 어셈블러를 사용하면 도구 공급업체는 IL 생성기를 쉽게 디자인하여 구현할 수 있으며,</span><span class="sxs-lookup"><span data-stu-id="0aca0-227">The IL Assembler helps tool vendors design and implement IL generators.</span></span> <span data-ttu-id="0aca0-228">*Ilasm.exe* 를 사용하면 도구 및 컴파일러 개발자는 IL을 PE 파일 형식으로 내보내는 것에 신경 쓰지 않고 IL 및 메타데이터 생성에만 몰두할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-228">Using *Ilasm.exe*, tool and compiler developers can concentrate on IL and metadata generation without being concerned with emitting IL in the PE file format.</span></span>

<span data-ttu-id="0aca0-229">*Ilasm.exe* 를 사용하면 C# 및 Visual Basic과 같이 런타임을 대상으로 하는 다른 컴파일러처럼 중간 개체 파일이 생성되지 않으며 PE 파일을 만들 때 링크하는 단계가 필요 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-229">Similar to other compilers that target the runtime, such as C# and Visual Basic, *Ilasm.exe* does not produce intermediate object files and does not require a linking stage to form a PE file.</span></span>

<span data-ttu-id="0aca0-230">IL 어셈블러를 사용하면 런타임을 대상으로 하는 프로그래밍 언어의 IL 기능 및 기존 메타데이터를 모두 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-230">The IL Assembler can express all the existing metadata and IL features of the programming languages that target the runtime.</span></span> <span data-ttu-id="0aca0-231">이렇게 하면 이러한 프로그래밍 언어로 작성된 관리 코드를 IL 어셈블러에서 적절히 표현하고 *Ilasm.exe* 를 사용하여 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-231">This allows managed code written in any of these programming languages to be adequately expressed in IL Assembler and compiled with *Ilasm.exe*.</span></span>

> [!NOTE]
> <span data-ttu-id="0aca0-232">.il 소스 파일의 마지막 코드 줄에 후행 공백이나 줄 끝(EOL) 문자가 없으면 컴파일이 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-232">Compilation might fail if the last line of code in the .il source file does not have either trailing white space or an end-of-line character.</span></span>

<span data-ttu-id="0aca0-233">*Ilasm.exe* 는 자매 도구인 [*Ildasm.exe*](ildasm-exe-il-disassembler.md)와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-233">You can use *Ilasm.exe* in conjunction with its companion tool, [*Ildasm.exe*](ildasm-exe-il-disassembler.md).</span></span> <span data-ttu-id="0aca0-234">*Ildasm.exe* 는 IL 코드가 포함된 PE 파일을 가져와서 *Ildasm.exe* 에 입력하기에 적합한 텍스트 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-234">*Ildasm.exe* takes a PE file that contains IL code and creates a text file suitable as input to *Ilasm.exe*.</span></span> <span data-ttu-id="0aca0-235">이렇게 하면 런타임 메타데이터 특성을 모두 지원하지 않는 프로그래밍 언어로 코드를 컴파일할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-235">This is useful, for example, when compiling code in a programming language that does not support all the runtime metadata attributes.</span></span> <span data-ttu-id="0aca0-236">코드를 컴파일하고 *Ildasm.exe* 를 사용하여 출력을 실행한 후에는 결과로 만들어지는 IL 텍스트 파일을 수동으로 편집하여 손실된 특성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-236">After compiling the code and running the output through *Ildasm.exe*, the resulting IL text file can be hand-edited to add the missing attributes.</span></span> <span data-ttu-id="0aca0-237">그런 다음에는 *Ilasm.exe* 를 통해 이 텍스트 파일을 실행하여 최종 실행 파일을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-237">You can then run this text file through the *Ilasm.exe* to produce a final executable file.</span></span>

<span data-ttu-id="0aca0-238">또한, 이 기술을 사용하면 서로 다른 컴파일러에서 생성된 여러 개의 PE 파일에서 하나의 PE 파일을 생성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-238">You can also use this technique to produce a single PE file from several PE files originally generated by different compilers.</span></span>

> [!NOTE]
> <span data-ttu-id="0aca0-239">포함된 네이티브 코드가 들어 있는 PE 파일(예: Visual C++로 생성된 PE 파일)에는 현재 이 방법을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-239">Currently, you cannot use this technique with PE files that contain embedded native code (for example, PE files produced by Visual C++).</span></span>

<span data-ttu-id="0aca0-240">가능한 정확하게 *Ildasm.exe* 및 *Ilasm.exe* 를 복합적으로 사용하려면, 디폴트로 어셈블러가 IL 소스에서 기록한 (혹은 다른 컴파일러에 의하여 빠뜨려진) 긴 인코딩에 대한 짧은 인코딩을 대체하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-240">To make this combined use of *Ildasm.exe* and *Ilasm.exe* as accurate as possible, by default the assembler does not substitute short encodings for long ones you might have written in your IL sources (or that might be emitted by another compiler).</span></span> <span data-ttu-id="0aca0-241">**/optimize** 옵션을 사용하여 가능한 짧은 인코딩으로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-241">Use the **/optimize** option to substitute short encodings wherever possible.</span></span>

> [!NOTE]
> <span data-ttu-id="0aca0-242">*Ildasm.exe* 는 디스크의 파일에 대해서만 작동하며,</span><span class="sxs-lookup"><span data-stu-id="0aca0-242">*Ildasm.exe* only operates on files on disk.</span></span> <span data-ttu-id="0aca0-243">전역 어셈블리 캐시에 설치된 파일에 대해서는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-243">It does not operate on files installed in the global assembly cache.</span></span>

<span data-ttu-id="0aca0-244">IL 문법에 대한 자세한 내용은 Windows SDK에서 asmparse.grammar 파일을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0aca0-244">For more information about the grammar of IL, see the asmparse.grammar file in the Windows SDK.</span></span>

## <a name="version-information"></a><span data-ttu-id="0aca0-245">버전 정보</span><span class="sxs-lookup"><span data-stu-id="0aca0-245">Version Information</span></span>

<span data-ttu-id="0aca0-246">.NET Framework 4.5부터 다음과 같은 코드를 사용하여 사용자 지정 특성을 인터페이스 구현에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-246">Starting with the .NET Framework 4.5, you can attach a custom attribute to an interface implementation by using code similar to the following:</span></span>

```il
.class interface public abstract auto ansi IMyInterface
{
  .method public hidebysig newslot abstract virtual
    instance int32 method1() cil managed
  {
  } // end of method IMyInterface::method1
} // end of class IMyInterface
.class public auto ansi beforefieldinit MyClass
  extends [mscorlib]System.Object
  implements IMyInterface
  {
    .interfaceimpl type IMyInterface
    .custom instance void
      [mscorlib]System.Diagnostics.DebuggerNonUserCodeAttribute::.ctor() = ( 01 00 00 00 )
      …
```

<span data-ttu-id="0aca0-247">.NET Framework 4.5부터 다음 코드와 같이 원시 이진 표현을 사용하여 임의의 마샬 BLOB(이진 대형 개체)을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-247">Starting with the .NET Framework 4.5, you can specify an arbitrary marshal BLOB (binary large object) by using its raw binary representation, as shown in the following code:</span></span>

```il
.method public hidebysig abstract virtual
        instance void
        marshal({ 38 01 02 FF })
        Test(object A_1) cil managed
```

<span data-ttu-id="0aca0-248">IL 문법에 대한 자세한 내용은 Windows SDK에서 asmparse.grammar 파일을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0aca0-248">For more information about the grammar of IL, see the asmparse.grammar file in the Windows SDK.</span></span>

## <a name="examples"></a><span data-ttu-id="0aca0-249">예</span><span class="sxs-lookup"><span data-stu-id="0aca0-249">Examples</span></span>

<span data-ttu-id="0aca0-250">다음 명령은 IL 파일 *myTestFile.il* 을 어셈블하고 실행 파일 *myTestFile.exe* 를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-250">The following command assembles the IL file *myTestFile.il* and produces the executable *myTestFile.exe*.</span></span>

```console
ilasm myTestFile
```

<span data-ttu-id="0aca0-251">다음 명령은 IL 파일 *myTestFile.il* 을 어셈블하고 *.dll* 파일 *myTestFile.dll* 을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-251">The following command assembles the IL file *myTestFile.il* and produces the *.dll* file *myTestFile.dll*.</span></span>

```console
ilasm myTestFile /dll
```

<span data-ttu-id="0aca0-252">다음 명령은 IL 파일 *myTestFile.il* 을 어셈블하고 *.dll* 파일 *myNewTestFile.dll* 을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-252">The following command assembles the IL file *myTestFile.il* and produces the *.dll* file *myNewTestFile.dll*.</span></span>

```console
ilasm myTestFile /dll /output:myNewTestFile.dll
```

<span data-ttu-id="0aca0-253">다음 코드 예제에서는 "Hello World!"를 콘솔에 표시하는 매우 간단한 애플리케이션을</span><span class="sxs-lookup"><span data-stu-id="0aca0-253">The following code example shows an extremely simple application that displays "Hello World!"</span></span> <span data-ttu-id="0aca0-254">표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-254">to the console.</span></span> <span data-ttu-id="0aca0-255">이 코드를 컴파일한 다음 [*Ildasm.exe*](ildasm-exe-il-disassembler.md) 도구를 사용하여 IL 파일을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-255">You can compile this code and then use the [*Ildasm.exe*](ildasm-exe-il-disassembler.md) tool to generate an IL file.</span></span>

```csharp
using System;

public class Hello
{
    public static void Main(String[] args)
    {
        Console.WriteLine("Hello World!");
    }
}
```

<span data-ttu-id="0aca0-256">다음 IL 코드 예제는 이전 C# 코드 예제에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-256">The following IL code example corresponds to the previous C# code example.</span></span> <span data-ttu-id="0aca0-257">IL 어셈블러 도구를 사용하여 이 코드를 어셈블리로 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-257">You can compile this code into an assembly using the IL Assembler tool.</span></span> <span data-ttu-id="0aca0-258">IL과 C# 코드 예제 모두 콘솔에 "Hello World!"를</span><span class="sxs-lookup"><span data-stu-id="0aca0-258">Both IL and C# code examples display "Hello World!"</span></span> <span data-ttu-id="0aca0-259">표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0aca0-259">to the console.</span></span>

```il
// Metadata version: v2.0.50215
.assembly extern mscorlib
{
  .publickeytoken = (B7 7A 5C 56 19 34 E0 89 )                         // .z\V.4..
  .ver 2:0:0:0
}
.assembly sample
{
  .custom instance void [mscorlib]System.Runtime.CompilerServices.CompilationRelaxationsAttribute::.ctor(int32) = ( 01 00 08 00 00 00 00 00 )
  .hash algorithm 0x00008004
  .ver 0:0:0:0
}
.module sample.exe
// MVID: {A224F460-A049-4A03-9E71-80A36DBBBCD3}
.imagebase 0x00400000
.file alignment 0x00000200
.stackreserve 0x00100000
.subsystem 0x0003       // WINDOWS_CUI
.corflags 0x00000001    //  ILONLY
// Image base: 0x02F20000

// =============== CLASS MEMBERS DECLARATION ===================

.class public auto ansi beforefieldinit Hello
       extends [mscorlib]System.Object
{
  .method public hidebysig static void  Main(string[] args) cil managed
  {
    .entrypoint
    // Code size       13 (0xd)
    .maxstack  8
    IL_0000:  nop
    IL_0001:  ldstr      "Hello World!"
    IL_0006:  call       void [mscorlib]System.Console::WriteLine(string)
    IL_000b:  nop
    IL_000c:  ret
  } // end of method Hello::Main

  .method public hidebysig specialname rtspecialname
          instance void  .ctor() cil managed
  {
    // Code size       7 (0x7)
    .maxstack  8
    IL_0000:  ldarg.0
    IL_0001:  call       instance void [mscorlib]System.Object::.ctor()
    IL_0006:  ret
  } // end of method Hello::.ctor

} // end of class Hello
```

## <a name="see-also"></a><span data-ttu-id="0aca0-260">참조</span><span class="sxs-lookup"><span data-stu-id="0aca0-260">See also</span></span>

- [<span data-ttu-id="0aca0-261">도구</span><span class="sxs-lookup"><span data-stu-id="0aca0-261">Tools</span></span>](index.md)
- [<span data-ttu-id="0aca0-262">*Ildasm.exe*(IL 디스어셈블러)</span><span class="sxs-lookup"><span data-stu-id="0aca0-262">*Ildasm.exe* (IL Disassembler)</span></span>](ildasm-exe-il-disassembler.md)
- [<span data-ttu-id="0aca0-263">관리되는 실행 프로세스</span><span class="sxs-lookup"><span data-stu-id="0aca0-263">Managed Execution Process</span></span>](../../standard/managed-execution-process.md)
- [<span data-ttu-id="0aca0-264">개발자 명령줄 셸</span><span class="sxs-lookup"><span data-stu-id="0aca0-264">Developer command-line shells</span></span>](/visualstudio/ide/reference/command-prompt-powershell)
