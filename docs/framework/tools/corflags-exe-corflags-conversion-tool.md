---
title: CorFlags.exe(CorFlags 변환 도구)
ms.date: 03/30/2017
helpviewer_keywords:
- CorFlags conversion tool
- CorFlags.exe
- portable executable files, CorFlags section
ms.assetid: ef900f8f-71ca-4dde-9b8c-95ddb0d7d89c
ms.openlocfilehash: e1251b6660db45f3af4f6e57114b1b10da18bd0a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "73129857"
---
# <a name="corflagsexe-corflags-conversion-tool"></a><span data-ttu-id="5cd5d-102">CorFlags.exe(CorFlags 변환 도구)</span><span class="sxs-lookup"><span data-stu-id="5cd5d-102">CorFlags.exe (CorFlags Conversion Tool)</span></span>
<span data-ttu-id="5cd5d-103">CorFlags 변환 도구를 사용하면 이식할 수 있는 실행 가능 이미지 헤더의 CorFlags 섹션을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cd5d-103">The CorFlags Conversion tool allows you to configure the CorFlags section of the header of a portable executable image.</span></span>  
  
 <span data-ttu-id="5cd5d-104">이 도구는 자동으로 Visual Studio와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cd5d-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="5cd5d-105">이 도구를 실행하려면 Visual Studio용 개발자 명령 프롬프트(또는 Windows 7의 Visual Studio 명령 프롬프트)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd5d-105">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="5cd5d-106">자세한 내용은 [명령 프롬프트](developer-command-prompt-for-vs.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5cd5d-106">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="5cd5d-107">명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd5d-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cd5d-108">구문</span><span class="sxs-lookup"><span data-stu-id="5cd5d-108">Syntax</span></span>  
  
```console  
CorFlags.exe assembly [options]  
```  
  
## <a name="parameters"></a><span data-ttu-id="5cd5d-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5cd5d-109">Parameters</span></span>  
  
|<span data-ttu-id="5cd5d-110">필수적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="5cd5d-110">Required parameter</span></span>|<span data-ttu-id="5cd5d-111">설명</span><span class="sxs-lookup"><span data-stu-id="5cd5d-111">Description</span></span>|  
|------------------------|-----------------|  
|`assembly`|<span data-ttu-id="5cd5d-112">CorFlags를 구성할 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5cd5d-112">The name of the assembly for which to configure the CorFlags.</span></span>|  
  
|<span data-ttu-id="5cd5d-113">옵션</span><span class="sxs-lookup"><span data-stu-id="5cd5d-113">Option</span></span>|<span data-ttu-id="5cd5d-114">설명</span><span class="sxs-lookup"><span data-stu-id="5cd5d-114">Description</span></span>|  
|:------------|-----------------|  
|`-32BIT[REQ]+`|<span data-ttu-id="5cd5d-115">32BITREQUIRED 플래그를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd5d-115">Sets the 32BITREQUIRED flag.</span></span>|  
|`-32BIT[REQ]-`|<span data-ttu-id="5cd5d-116">32BITREQUIRED 플래그를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="5cd5d-116">Clears the 32BITREQUIRED flag.</span></span>|  
|`-32BITPREF+`|<span data-ttu-id="5cd5d-117">32BITPREFERRED 플래그를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd5d-117">Sets the 32BITPREFERRED flag.</span></span> <span data-ttu-id="5cd5d-118">응용 프로그램이 64비트 플랫폼에서 32비트 프로세스로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cd5d-118">The app runs as a 32-bit process even on 64-bit platforms.</span></span> <span data-ttu-id="5cd5d-119">EXE 파일에만 이 플래그를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd5d-119">Set this flag only on EXE files.</span></span> <span data-ttu-id="5cd5d-120">DLL에 플래그가 설정되면 DLL은 64비트 프로세스 로드에 실패하고 <xref:System.BadImageFormatException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cd5d-120">If the flag is set on a DLL, the DLL fails to load in 64-bit processes, and a <xref:System.BadImageFormatException> exception is thrown.</span></span> <span data-ttu-id="5cd5d-121">이 플래그를 사용하여 EXE 파일은 64비트 프로세스에 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5cd5d-121">An EXE file with this flag can be loaded into a 64-bit process.</span></span><br /><br /> <span data-ttu-id="5cd5d-122">.NET Framework 4.5의 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="5cd5d-122">New in the .NET Framework 4.5.</span></span>|  
|`-32BITPREF-`|<span data-ttu-id="5cd5d-123">32BITPREFERRED 플래그를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="5cd5d-123">Clears the 32BITPREFERRED flag.</span></span><br /><br /> <span data-ttu-id="5cd5d-124">.NET Framework 4.5의 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="5cd5d-124">New in the .NET Framework 4.5.</span></span>|  
|`-?`|<span data-ttu-id="5cd5d-125">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd5d-125">Displays command syntax and options for the tool.</span></span>|  
|`-Force`|<span data-ttu-id="5cd5d-126">어셈블리의 이름이 강력한 이름인 경우에도 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd5d-126">Forces an update even if the assembly is strong-named.</span></span> <span data-ttu-id="5cd5d-127">**중요:** 강력한 이름의 어셈블리를 업데이트하면 코드를 실행하기 전에 다시 서명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd5d-127">**Important:**  If you update a strong-named assembly, you must sign it again before executing its code.</span></span>|  
|`-help`|<span data-ttu-id="5cd5d-128">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd5d-128">Displays command syntax and options for the tool.</span></span>|  
|`-ILONLY+`|<span data-ttu-id="5cd5d-129">ILONLY 플래그를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd5d-129">Sets the ILONLY flag.</span></span>|  
|`-ILONLY-`|<span data-ttu-id="5cd5d-130">ILONLY 플래그를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="5cd5d-130">Clears the ILONLY flag.</span></span>|  
|`-nologo`|<span data-ttu-id="5cd5d-131">Microsoft 시작 배너를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5cd5d-131">Suppresses the Microsoft startup banner display.</span></span>|  
|`-RevertCLRHeader`|<span data-ttu-id="5cd5d-132">CLR 헤더 버전을 2.0으로 되돌립니다.</span><span class="sxs-lookup"><span data-stu-id="5cd5d-132">Reverts the CLR header version to 2.0.</span></span>|  
|`-UpgradeCLRHeader`|<span data-ttu-id="5cd5d-133">CLR 헤더 버전을 2.5로 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd5d-133">Upgrades the CLR header version to 2.5.</span></span> <span data-ttu-id="5cd5d-134">**참고:** 기본적으로 어셈블리를 실행하려면 CLR 헤더 버전이 2.5 이상이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd5d-134">**Note:**  Assemblies must have a CLR header version of 2.5 or greater to run natively.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5cd5d-135">설명</span><span class="sxs-lookup"><span data-stu-id="5cd5d-135">Remarks</span></span>  
 <span data-ttu-id="5cd5d-136">옵션을 지정하지 않으면 CorFlags 변환 도구에서 지정한 어셈블리에 대한 플래그를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5cd5d-136">If no options are specified, the CorFlags Conversion tool displays the flags for the specified assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cd5d-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5cd5d-137">See also</span></span>

- [<span data-ttu-id="5cd5d-138">도구</span><span class="sxs-lookup"><span data-stu-id="5cd5d-138">Tools</span></span>](index.md)
- [<span data-ttu-id="5cd5d-139">64비트 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="5cd5d-139">64-bit Applications</span></span>](../64-bit-apps.md)
- [<span data-ttu-id="5cd5d-140">명령 프롬프트</span><span class="sxs-lookup"><span data-stu-id="5cd5d-140">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
