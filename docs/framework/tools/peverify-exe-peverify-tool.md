---
title: Peverify.exe(PEVerify 도구)
description: Peverify.exe(이식 가능한 실행 파일 확인)를 사용하면 MSIL(Microsoft 중간 언어) 코드 및 메타데이터가 .NET의 형식 안전성 표준을 충족하는지 확인할 수 있습니다.
ms.date: 03/30/2017
helpviewer_keywords:
- portable executable files, PEVerify
- verifying MSIL and metadata
- PEVerify tool
- type safety requirements
- MSIL
- PEverify.exe
- PE files, PEVerify
ms.assetid: f4f46f9e-8d08-4e66-a94b-0c69c9b0bbfa
ms.openlocfilehash: ba8b4cd7f398eee9129d24d25d8fdb754c89a3ee
ms.sourcegitcommit: 1dbe25ff484a02025d5c34146e517c236f7161fb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "104653298"
---
# <a name="peverifyexe-peverify-tool"></a><span data-ttu-id="6855e-103">Peverify.exe(PEVerify 도구)</span><span class="sxs-lookup"><span data-stu-id="6855e-103">Peverify.exe (PEVerify tool)</span></span>

<span data-ttu-id="6855e-104">MSIL(Microsoft 중간 언어)을 생성하는 개발자(컴파일러 작성자, 스크립트 엔진 개발자 등)는 PEVerify 도구를 사용하여 MSIL 코드 및 관련 메타데이터가 형식 안전성 요구 사항을 충족하는지 쉽게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-104">The PEVerify tool helps developers who generate Microsoft intermediate language (MSIL) (such as compiler writers and script engine developers) to determine whether their MSIL code and associated metadata meet type safety requirements.</span></span> <span data-ttu-id="6855e-105">일부 컴파일러에서는 특정 언어 구문을 사용하지 않는 경우에만 확인 가능한 형식 안전 코드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-105">Some compilers generate verifiably type-safe code only if you avoid using certain language constructs.</span></span> <span data-ttu-id="6855e-106">이러한 컴파일러를 사용하는 경우 해당 코드의 형식 안전성이 손상되지 않았는지 확인하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-106">If you're using such a compiler, you may want to verify that you have not compromised the type safety of your code.</span></span> <span data-ttu-id="6855e-107">해당 파일에 대해 PEVerify 도구를 실행하면 MSIL 및 메타데이터를 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-107">You can run the PEVerify tool on your files to check the MSIL and metadata.</span></span>  
  
 <span data-ttu-id="6855e-108">이 도구는 자동으로 Visual Studio와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-108">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="6855e-109">도구를 실행하려면 [Visual Studio 개발자 명령 프롬프트 또는 Visual Studio 개발자 PowerShell](/visualstudio/ide/reference/command-prompt-powershell)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-109">To run the tool, use [Visual Studio Developer Command Prompt or Visual Studio Developer PowerShell](/visualstudio/ide/reference/command-prompt-powershell).</span></span>
  
## <a name="syntax"></a><span data-ttu-id="6855e-110">구문</span><span class="sxs-lookup"><span data-stu-id="6855e-110">Syntax</span></span>  
  
```console  
peverify filename [options]  
```  
  
## <a name="parameters"></a><span data-ttu-id="6855e-111">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6855e-111">Parameters</span></span>  
  
|<span data-ttu-id="6855e-112">인수</span><span class="sxs-lookup"><span data-stu-id="6855e-112">Argument</span></span>|<span data-ttu-id="6855e-113">설명</span><span class="sxs-lookup"><span data-stu-id="6855e-113">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="6855e-114">*filename*</span><span class="sxs-lookup"><span data-stu-id="6855e-114">*filename*</span></span>|<span data-ttu-id="6855e-115">MSIL 및 메타데이터를 검사할 대상 PE(이식 가능한 실행) 파일을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-115">The portable executable (PE) file for which to check the MSIL and metadata.</span></span>|  
  
|<span data-ttu-id="6855e-116">옵션</span><span class="sxs-lookup"><span data-stu-id="6855e-116">Option</span></span>|<span data-ttu-id="6855e-117">설명</span><span class="sxs-lookup"><span data-stu-id="6855e-117">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="6855e-118">**/break=** *maxErrorCount*</span><span class="sxs-lookup"><span data-stu-id="6855e-118">**/break=** *maxErrorCount*</span></span>|<span data-ttu-id="6855e-119">*maxErrorCount* 오류가 발생하면 확인을 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-119">Aborts verification after *maxErrorCount* errors.</span></span><br /><br /> <span data-ttu-id="6855e-120">이 매개 변수는 .NET Framework 버전 2.0 이상에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-120">This parameter is not supported in .NET Framework version 2.0 or later.</span></span>|  
|<span data-ttu-id="6855e-121">**/clock**</span><span class="sxs-lookup"><span data-stu-id="6855e-121">**/clock**</span></span>|<span data-ttu-id="6855e-122">다음 확인 시간을 밀리초 단위로 측정하여 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-122">Measures and reports the following verification times in milliseconds:</span></span><br /><br /> <span data-ttu-id="6855e-123">**MD Val. cycle**</span><span class="sxs-lookup"><span data-stu-id="6855e-123">**MD Val. cycle**</span></span><br /> <span data-ttu-id="6855e-124">메타데이터 유효성 검사 순환</span><span class="sxs-lookup"><span data-stu-id="6855e-124">Metadata validation cycle</span></span><br /><br /> <span data-ttu-id="6855e-125">**MD Val. pure**</span><span class="sxs-lookup"><span data-stu-id="6855e-125">**MD Val. pure**</span></span><br /> <span data-ttu-id="6855e-126">메타데이터 유효성 검사 순수</span><span class="sxs-lookup"><span data-stu-id="6855e-126">Metadata validation pure</span></span><br /><br /> <span data-ttu-id="6855e-127">**IL Ver. cycle**</span><span class="sxs-lookup"><span data-stu-id="6855e-127">**IL Ver. cycle**</span></span><br /> <span data-ttu-id="6855e-128">MSIL(Microsoft Intermediate Language) 확인 순환</span><span class="sxs-lookup"><span data-stu-id="6855e-128">Microsoft intermediate language (MSIL) verification cycle</span></span><br /><br /> <span data-ttu-id="6855e-129">**IL Ver pure**</span><span class="sxs-lookup"><span data-stu-id="6855e-129">**IL Ver pure**</span></span><br /> <span data-ttu-id="6855e-130">MSIL 확인 순수</span><span class="sxs-lookup"><span data-stu-id="6855e-130">MSIL verification pure</span></span><br /><br /> <span data-ttu-id="6855e-131">**MD Val. cycle** 및 **IL Ver. cycle** 시간에는 필수 시작 및 종료 프로시저를 수행하는 데 필요한 시간이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-131">The **MD Val. cycle** and **IL Ver. cycle** times include the time required to perform necessary startup and shutdown procedures.</span></span> <span data-ttu-id="6855e-132">**MD Val. pure** 및 **IL Ver pure** 시간에는 유효성 검사 또는 확인만 수행하는 데 필요한 시간이 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-132">The **MD Val. pure** and **IL Ver pure** times reflect the time required to perform the validation or verification only.</span></span>|  
|<span data-ttu-id="6855e-133">**/help**</span><span class="sxs-lookup"><span data-stu-id="6855e-133">**/help**</span></span>|<span data-ttu-id="6855e-134">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-134">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="6855e-135">**/hresult**</span><span class="sxs-lookup"><span data-stu-id="6855e-135">**/hresult**</span></span>|<span data-ttu-id="6855e-136">16진수 형식의 오류 코드를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-136">Displays error codes in hexadecimal format.</span></span>|  
|<span data-ttu-id="6855e-137">**/ignore=** *hex.code* [, *hex.code*]</span><span class="sxs-lookup"><span data-stu-id="6855e-137">**/ignore=** *hex.code* [, *hex.code*]</span></span>|<span data-ttu-id="6855e-138">지정된 오류 코드를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-138">Ignores the specified error codes.</span></span>|  
|<span data-ttu-id="6855e-139">**/ignore=@** *responseFile*</span><span class="sxs-lookup"><span data-stu-id="6855e-139">**/ignore=@** *responseFile*</span></span>|<span data-ttu-id="6855e-140">지정된 지시 파일에 나열된 오류 코드를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-140">Ignores the error codes listed in the specified response file.</span></span>|  
|<span data-ttu-id="6855e-141">**/il**</span><span class="sxs-lookup"><span data-stu-id="6855e-141">**/il**</span></span>|<span data-ttu-id="6855e-142">*filename* 으로 지정된 어셈블리에 구현된 메서드에 대해 MSIL 형식 안전성 확인 검사를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-142">Performs MSIL type safety verification checks for methods implemented in the assembly specified by *filename*.</span></span> <span data-ttu-id="6855e-143">**/quiet** 옵션을 지정하지 않으면 발견된 각 문제점에 대해 자세한 설명이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-143">The tool returns detailed descriptions for each problem found unless you specify the **/quiet** option.</span></span>|  
|<span data-ttu-id="6855e-144">**/md**</span><span class="sxs-lookup"><span data-stu-id="6855e-144">**/md**</span></span>|<span data-ttu-id="6855e-145">*filename* 으로 지정된 어셈블리에 대해 메타데이터 유효성 검사를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-145">Performs metadata validation checks on the assembly specified by *filename*.</span></span> <span data-ttu-id="6855e-146">이 옵션은 파일 내의 전체 메타데이터 구조에 대해 수행되며, 발생한 모든 유효성 검사 문제를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-146">This option walks the full metadata structure within the file and reports all validation problems encountered.</span></span>|  
|<span data-ttu-id="6855e-147">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="6855e-147">**/nologo**</span></span>|<span data-ttu-id="6855e-148">제품 버전과 저작권 정보를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-148">Suppresses the display of product version and copyright information.</span></span>|  
|<span data-ttu-id="6855e-149">**/nosymbols**</span><span class="sxs-lookup"><span data-stu-id="6855e-149">**/nosymbols**</span></span>|<span data-ttu-id="6855e-150">.NET Framework 버전 2.0에서 이전 버전과의 호환성에 대한 줄 번호를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-150">In the .NET Framework version 2.0, suppresses line numbers for backward compatibility.</span></span>|  
|<span data-ttu-id="6855e-151">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="6855e-151">**/quiet**</span></span>|<span data-ttu-id="6855e-152">자동 모드를 지정합니다. 즉, 확인 문제 보고서를 출력하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-152">Specifies quiet mode; suppresses output of the verification problem reports.</span></span> <span data-ttu-id="6855e-153">Peverify.exe를 통해 파일의 형식 안전성 여부는 보고되지만, 형식 안전성 확인을 방해하는 문제점에 대한 정보는 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-153">Peverify.exe still reports whether the file is type safe, but does not report information on problems preventing type safety verification.</span></span>|  
|`/transparent`|<span data-ttu-id="6855e-154">투명 메서드만 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-154">Verify only the transparent methods.</span></span>|  
|<span data-ttu-id="6855e-155">**/unique**</span><span class="sxs-lookup"><span data-stu-id="6855e-155">**/unique**</span></span>|<span data-ttu-id="6855e-156">반복되는 오류 코드를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-156">Ignores repeating error codes.</span></span>|  
|<span data-ttu-id="6855e-157">**/verbose**</span><span class="sxs-lookup"><span data-stu-id="6855e-157">**/verbose**</span></span>|<span data-ttu-id="6855e-158">.NET Framework 버전 2.0에서 MSIL 확인 메시지에 추가 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-158">In the .NET Framework version 2.0, displays additional information in MSIL verification messages.</span></span>|  
|<span data-ttu-id="6855e-159">**/?**</span><span class="sxs-lookup"><span data-stu-id="6855e-159">**/?**</span></span>|<span data-ttu-id="6855e-160">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-160">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6855e-161">설명</span><span class="sxs-lookup"><span data-stu-id="6855e-161">Remarks</span></span>  

 <span data-ttu-id="6855e-162">공용 언어 런타임에서는 애플리케이션 코드의 형식 안전 실행을 통해 보안 및 격리 메커니즘을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-162">The common language runtime relies on the type-safe execution of application code to help enforce security and isolation mechanisms.</span></span> <span data-ttu-id="6855e-163">일반적으로 [확인할 수 있도록 형식이 안전](../../standard/security/key-security-concepts.md#type-safety-and-security)</span><span class="sxs-lookup"><span data-stu-id="6855e-163">Normally, code that is not [verifiably type safe](../../standard/security/key-security-concepts.md#type-safety-and-security) cannot run, although you can set security policy to allow the execution of trusted but unverifiable code.</span></span>  
  
 <span data-ttu-id="6855e-164">**/md** 및 **/il** 옵션이 모두 지정되지 않은 경우 Peverify.exe를 사용하면 두 종류의 검사를 모두 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-164">If neither the **/md** nor **/il** options are specified, Peverify.exe performs both types of checks.</span></span> <span data-ttu-id="6855e-165">먼저 **/md** 검사가 수행되고,</span><span class="sxs-lookup"><span data-stu-id="6855e-165">Peverify.exe performs **/md** checks first.</span></span> <span data-ttu-id="6855e-166">오류가 없으면 **/il** 검사가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-166">If there are no errors, **/il** checks are made.</span></span> <span data-ttu-id="6855e-167">**/md** 및 **/il** 을 모두 지정하면 메타데이터에 오류가 있는 경우에도 **/il** 검사가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-167">If you specify both **/md** and **/il**, **/il** checks are made even if there are errors in the metadata.</span></span> <span data-ttu-id="6855e-168">따라서 메타데이터 오류가 없는 경우 **peverify** *filename* 은 **peverify** *filename* **/md** **/il** 과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-168">Thus, if there are no metadata errors, **peverify** *filename* is equivalent to **peverify** *filename* **/md** **/il**.</span></span>  
  
 <span data-ttu-id="6855e-169">Peverify.exe를 사용하여 데이터 흐름 분석과 올바른 메타데이터에 대한 수백 개의 규칙 목록에 따라 포괄적인 MSIL 확인 검사를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-169">Peverify.exe performs comprehensive MSIL verification checks based on dataflow analysis plus a list of several hundred rules on valid metadata.</span></span> <span data-ttu-id="6855e-170">Peverify.exe를 사용하여 수행하는 검사에 대한 자세한 내용은 Windows SDK의 Tools Developers Guide 폴더에 있는 "메타데이터 유효성 검사 사양" 및 "MSIL 명령 집합 사양"을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6855e-170">For detailed information on the checks Peverify.exe performs, see the "Metadata Validation Specification" and the "MSIL Instruction Set Specification" in the Tools Developers Guide folder in the Windows SDK.</span></span>  
  
<span data-ttu-id="6855e-171">.NET Framework 버전 2.0 이상은 `dup`, `ldsflda`, `ldflda`, `ldelema`, `call`, `unbox` 등의 MSIL 지침을 사용하여 지정된 확인할 수 있는 `byref` 반환을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-171">.NET Framework version 2.0 or later supports verifiable `byref` returns specified using the following MSIL instructions: `dup`, `ldsflda`, `ldflda`, `ldelema`, `call`, and `unbox`.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="6855e-172">예</span><span class="sxs-lookup"><span data-stu-id="6855e-172">Examples</span></span>  

 <span data-ttu-id="6855e-173">다음 명령을 사용하여 어셈블리 `myAssembly.exe`에 구현된 메서드에 대해 메타데이터 유효성 검사 및 MSIL 형식 안전성 확인 검사를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-173">The following command performs metadata validation checks and MSIL type safety verification checks for methods implemented in the assembly `myAssembly.exe`.</span></span>  
  
```console  
peverify myAssembly.exe /md /il  
```  
  
 <span data-ttu-id="6855e-174">위의 요청이 성공적으로 완료되면 Peverify.exe를 사용하여 다음과 같은 메시지를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-174">Upon successful completion of the above request, Peverify.exe displays the following message.</span></span>  
  
```output
All classes and methods in myAssembly.exe Verified  
```  
  
 <span data-ttu-id="6855e-175">다음 명령을 사용하여 어셈블리 `myAssembly.exe`에 구현된 메서드에 대해 메타데이터 유효성 검사 및 MSIL 형식 안전성 확인 검사를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-175">The following command performs metadata validation checks and MSIL type safety verification checks for methods implemented in the assembly `myAssembly.exe`.</span></span> <span data-ttu-id="6855e-176">도구에서는 이러한 확인을 수행하는 데 필요한 시간을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-176">The tool displays the time required to perform these checks.</span></span>  
  
```console  
peverify myAssembly.exe /md /il /clock  
```  
  
 <span data-ttu-id="6855e-177">위의 요청이 성공적으로 완료되면 Peverify.exe를 사용하여 다음과 같은 메시지를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-177">Upon successful completion of the above request, Peverify.exe displays the following message.</span></span>  
  
```output
All classes and methods in myAssembly.exe Verified  
Timing: Total run     320 msec  
        MD Val.cycle  40 msec  
        MD Val.pure   10 msec  
        IL Ver.cycle  270 msec  
        IL Ver.pure   230 msec  
```  
  
 <span data-ttu-id="6855e-178">다음 명령을 사용하여 어셈블리 `myAssembly.exe`에 구현된 메서드에 대해 메타데이터 유효성 검사 및 MSIL 형식 안전성 확인 검사를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-178">The following command performs metadata validation checks and MSIL type safety verification checks for methods implemented in the assembly `myAssembly.exe`.</span></span> <span data-ttu-id="6855e-179">그러나 최대 100의 오류 수에 도달하면 Peverify.exe를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-179">Peverify.exe stops, however, when it reaches the maximum error count of 100.</span></span> <span data-ttu-id="6855e-180">도구는 지정된 오류 코드를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-180">The tool also ignores the specified error codes.</span></span>  
  
```console  
peverify myAssembly.exe /break=100 /ignore=0x12345678,0xABCD1234  
```  
  
 <span data-ttu-id="6855e-181">다음 명령을 사용하여 앞의 예제와 동일한 결과를 생성하지만, 지시 파일 `ignoreErrors.rsp`에서 무시할 오류 코드를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-181">The following command produces the same result as the above previous example, but specifies the error codes to ignore in the response file `ignoreErrors.rsp`.</span></span>  
  
```console  
peverify myAssembly.exe /break=100 /ignore@ignoreErrors.rsp  
```  
  
 <span data-ttu-id="6855e-182">지시 파일에 다음과 같이 쉼표로 구분된 오류 코드 목록이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-182">The response file can contain a comma-separated list of error codes.</span></span>  
  
```text
0x12345678, 0xABCD1234  
```  
  
 <span data-ttu-id="6855e-183">또한, 다음과 같이 한 줄에 하나의 오류 코드가 오도록 지시 파일의 서식을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6855e-183">Alternatively, the response file can be formatted with one error code per line.</span></span>  
  
```text
0x12345678  
0xABCD1234  
```  
  
## <a name="see-also"></a><span data-ttu-id="6855e-184">참조</span><span class="sxs-lookup"><span data-stu-id="6855e-184">See also</span></span>

- [<span data-ttu-id="6855e-185">도구</span><span class="sxs-lookup"><span data-stu-id="6855e-185">Tools</span></span>](index.md)
- [<span data-ttu-id="6855e-186">형식 안정성이 확인된 코드 작성</span><span class="sxs-lookup"><span data-stu-id="6855e-186">Writing Verifiably Type-Safe Code</span></span>](../misc/code-access-security-basics.md#typesafe_code)
- [<span data-ttu-id="6855e-187">형식 안전성 및 보안</span><span class="sxs-lookup"><span data-stu-id="6855e-187">Type Safety and Security</span></span>](../../standard/security/key-security-concepts.md#type-safety-and-security)
- [<span data-ttu-id="6855e-188">개발자 명령줄 셸</span><span class="sxs-lookup"><span data-stu-id="6855e-188">Developer command-line shells</span></span>](/visualstudio/ide/reference/command-prompt-powershell)
