---
title: CorFlags.exe(CorFlags 변환 도구)
description: CorFlags.exe 즉, CorFlags 변환 도구를 이해합니다. 이 도구를 사용하면 이식 가능한 실행 이미지 헤더의 CorFlags 섹션을 구성할 수 있습니다.
ms.date: 03/30/2017
helpviewer_keywords:
- CorFlags conversion tool
- CorFlags.exe
- portable executable files, CorFlags section
ms.assetid: ef900f8f-71ca-4dde-9b8c-95ddb0d7d89c
ms.openlocfilehash: da5efadd63cc03f6f6e4eecf3115865ca3643b39
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167231"
---
# <a name="corflagsexe-corflags-conversion-tool"></a><span data-ttu-id="bc1e0-104">CorFlags.exe(CorFlags 변환 도구)</span><span class="sxs-lookup"><span data-stu-id="bc1e0-104">CorFlags.exe (CorFlags Conversion Tool)</span></span>
<span data-ttu-id="bc1e0-105">CorFlags 변환 도구를 사용하면 이식할 수 있는 실행 가능 이미지 헤더의 CorFlags 섹션을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e0-105">The CorFlags Conversion tool allows you to configure the CorFlags section of the header of a portable executable image.</span></span>  
  
 <span data-ttu-id="bc1e0-106">이 도구는 자동으로 Visual Studio와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e0-106">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="bc1e0-107">이 도구를 실행하려면 Visual Studio용 개발자 명령 프롬프트(또는 Windows 7의 Visual Studio 명령 프롬프트)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e0-107">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="bc1e0-108">자세한 내용은 [명령 프롬프트](developer-command-prompt-for-vs.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc1e0-108">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="bc1e0-109">명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e0-109">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc1e0-110">구문</span><span class="sxs-lookup"><span data-stu-id="bc1e0-110">Syntax</span></span>  
  
```console  
CorFlags.exe assembly [options]  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc1e0-111">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bc1e0-111">Parameters</span></span>  
  
|<span data-ttu-id="bc1e0-112">필수적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="bc1e0-112">Required parameter</span></span>|<span data-ttu-id="bc1e0-113">설명</span><span class="sxs-lookup"><span data-stu-id="bc1e0-113">Description</span></span>|  
|------------------------|-----------------|  
|`assembly`|<span data-ttu-id="bc1e0-114">CorFlags를 구성할 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e0-114">The name of the assembly for which to configure the CorFlags.</span></span>|  
  
|<span data-ttu-id="bc1e0-115">옵션</span><span class="sxs-lookup"><span data-stu-id="bc1e0-115">Option</span></span>|<span data-ttu-id="bc1e0-116">Description</span><span class="sxs-lookup"><span data-stu-id="bc1e0-116">Description</span></span>|  
|:------------|-----------------|  
|`-32BIT[REQ]+`|<span data-ttu-id="bc1e0-117">32BITREQUIRED 플래그를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e0-117">Sets the 32BITREQUIRED flag.</span></span>|  
|`-32BIT[REQ]-`|<span data-ttu-id="bc1e0-118">32BITREQUIRED 플래그를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e0-118">Clears the 32BITREQUIRED flag.</span></span>|  
|`-32BITPREF+`|<span data-ttu-id="bc1e0-119">32BITPREFERRED 플래그를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e0-119">Sets the 32BITPREFERRED flag.</span></span> <span data-ttu-id="bc1e0-120">응용 프로그램이 64비트 플랫폼에서 32비트 프로세스로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e0-120">The app runs as a 32-bit process even on 64-bit platforms.</span></span> <span data-ttu-id="bc1e0-121">EXE 파일에만 이 플래그를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e0-121">Set this flag only on EXE files.</span></span> <span data-ttu-id="bc1e0-122">DLL에 플래그가 설정되면 DLL은 64비트 프로세스 로드에 실패하고 <xref:System.BadImageFormatException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e0-122">If the flag is set on a DLL, the DLL fails to load in 64-bit processes, and a <xref:System.BadImageFormatException> exception is thrown.</span></span> <span data-ttu-id="bc1e0-123">이 플래그를 사용하여 EXE 파일은 64비트 프로세스에 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e0-123">An EXE file with this flag can be loaded into a 64-bit process.</span></span><br /><br /> <span data-ttu-id="bc1e0-124">.NET Framework 4.5의 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e0-124">New in the .NET Framework 4.5.</span></span>|  
|`-32BITPREF-`|<span data-ttu-id="bc1e0-125">32BITPREFERRED 플래그를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e0-125">Clears the 32BITPREFERRED flag.</span></span><br /><br /> <span data-ttu-id="bc1e0-126">.NET Framework 4.5의 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e0-126">New in the .NET Framework 4.5.</span></span>|  
|`-?`|<span data-ttu-id="bc1e0-127">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e0-127">Displays command syntax and options for the tool.</span></span>|  
|`-Force`|<span data-ttu-id="bc1e0-128">어셈블리의 이름이 강력한 이름인 경우에도 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e0-128">Forces an update even if the assembly is strong-named.</span></span> <span data-ttu-id="bc1e0-129">**중요:**  강력한 이름의 어셈블리를 업데이트하면 코드를 실행하기 전에 다시 서명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e0-129">**Important:**  If you update a strong-named assembly, you must sign it again before executing its code.</span></span>|  
|`-help`|<span data-ttu-id="bc1e0-130">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e0-130">Displays command syntax and options for the tool.</span></span>|  
|`-ILONLY+`|<span data-ttu-id="bc1e0-131">ILONLY 플래그를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e0-131">Sets the ILONLY flag.</span></span>|  
|`-ILONLY-`|<span data-ttu-id="bc1e0-132">ILONLY 플래그를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e0-132">Clears the ILONLY flag.</span></span>|  
|`-nologo`|<span data-ttu-id="bc1e0-133">Microsoft 시작 배너를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e0-133">Suppresses the Microsoft startup banner display.</span></span>|  
|`-RevertCLRHeader`|<span data-ttu-id="bc1e0-134">CLR 헤더 버전을 2.0으로 되돌립니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e0-134">Reverts the CLR header version to 2.0.</span></span>|  
|`-UpgradeCLRHeader`|<span data-ttu-id="bc1e0-135">CLR 헤더 버전을 2.5로 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e0-135">Upgrades the CLR header version to 2.5.</span></span> <span data-ttu-id="bc1e0-136">**참고:**  기본적으로 어셈블리를 실행하려면 CLR 헤더 버전이 2.5 이상이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e0-136">**Note:**  Assemblies must have a CLR header version of 2.5 or greater to run natively.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc1e0-137">설명</span><span class="sxs-lookup"><span data-stu-id="bc1e0-137">Remarks</span></span>  
 <span data-ttu-id="bc1e0-138">옵션을 지정하지 않으면 CorFlags 변환 도구에서 지정한 어셈블리에 대한 플래그를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="bc1e0-138">If no options are specified, the CorFlags Conversion tool displays the flags for the specified assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc1e0-139">참조</span><span class="sxs-lookup"><span data-stu-id="bc1e0-139">See also</span></span>

- [<span data-ttu-id="bc1e0-140">도구</span><span class="sxs-lookup"><span data-stu-id="bc1e0-140">Tools</span></span>](index.md)
- [<span data-ttu-id="bc1e0-141">64비트 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="bc1e0-141">64-bit Applications</span></span>](../64-bit-apps.md)
- [<span data-ttu-id="bc1e0-142">명령 프롬프트</span><span class="sxs-lookup"><span data-stu-id="bc1e0-142">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
