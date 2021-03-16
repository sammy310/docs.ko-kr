---
title: CorFlags.exe(CorFlags 변환 도구)
description: CorFlags.exe 즉, CorFlags 변환 도구를 이해합니다. 이 도구를 사용하면 이식 가능한 실행 이미지 헤더의 CorFlags 섹션을 구성할 수 있습니다.
ms.date: 03/30/2017
helpviewer_keywords:
- CorFlags conversion tool
- CorFlags.exe
- portable executable files, CorFlags section
ms.assetid: ef900f8f-71ca-4dde-9b8c-95ddb0d7d89c
ms.openlocfilehash: 4481e6718372fe7b58dbc05ab7cfe35e6d3047ce
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102258054"
---
# <a name="corflagsexe-corflags-conversion-tool"></a><span data-ttu-id="68729-104">CorFlags.exe(CorFlags 변환 도구)</span><span class="sxs-lookup"><span data-stu-id="68729-104">CorFlags.exe (CorFlags Conversion Tool)</span></span>

<span data-ttu-id="68729-105">CorFlags 변환 도구를 사용하면 이식할 수 있는 실행 가능 이미지 헤더의 CorFlags 섹션을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68729-105">The CorFlags Conversion tool allows you to configure the CorFlags section of the header of a portable executable image.</span></span>  
  
 <span data-ttu-id="68729-106">이 도구는 자동으로 Visual Studio와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="68729-106">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="68729-107">도구를 실행하려면 [개발자용 명령줄 셸](/visualstudio/ide/reference/command-prompt-powershell)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="68729-107">To run the tool, use a [command-line shell for developers](/visualstudio/ide/reference/command-prompt-powershell).</span></span>  
  
 <span data-ttu-id="68729-108">명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="68729-108">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68729-109">구문</span><span class="sxs-lookup"><span data-stu-id="68729-109">Syntax</span></span>  
  
```console  
CorFlags.exe assembly [options]  
```  
  
## <a name="parameters"></a><span data-ttu-id="68729-110">매개 변수</span><span class="sxs-lookup"><span data-stu-id="68729-110">Parameters</span></span>  
  
|<span data-ttu-id="68729-111">필수적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="68729-111">Required parameter</span></span>|<span data-ttu-id="68729-112">설명</span><span class="sxs-lookup"><span data-stu-id="68729-112">Description</span></span>|  
|------------------------|-----------------|  
|`assembly`|<span data-ttu-id="68729-113">CorFlags를 구성할 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="68729-113">The name of the assembly for which to configure the CorFlags.</span></span>|  
  
|<span data-ttu-id="68729-114">옵션</span><span class="sxs-lookup"><span data-stu-id="68729-114">Option</span></span>|<span data-ttu-id="68729-115">Description</span><span class="sxs-lookup"><span data-stu-id="68729-115">Description</span></span>|  
|:------------|-----------------|  
|`-32BIT[REQ]+`|<span data-ttu-id="68729-116">32BITREQUIRED 플래그를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="68729-116">Sets the 32BITREQUIRED flag.</span></span>|  
|`-32BIT[REQ]-`|<span data-ttu-id="68729-117">32BITREQUIRED 플래그를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="68729-117">Clears the 32BITREQUIRED flag.</span></span>|  
|`-32BITPREF+`|<span data-ttu-id="68729-118">32BITPREFERRED 플래그를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="68729-118">Sets the 32BITPREFERRED flag.</span></span> <span data-ttu-id="68729-119">응용 프로그램이 64비트 플랫폼에서 32비트 프로세스로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="68729-119">The app runs as a 32-bit process even on 64-bit platforms.</span></span> <span data-ttu-id="68729-120">EXE 파일에만 이 플래그를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="68729-120">Set this flag only on EXE files.</span></span> <span data-ttu-id="68729-121">DLL에 플래그가 설정되면 DLL은 64비트 프로세스 로드에 실패하고 <xref:System.BadImageFormatException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="68729-121">If the flag is set on a DLL, the DLL fails to load in 64-bit processes, and a <xref:System.BadImageFormatException> exception is thrown.</span></span> <span data-ttu-id="68729-122">이 플래그를 사용하여 EXE 파일은 64비트 프로세스에 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68729-122">An EXE file with this flag can be loaded into a 64-bit process.</span></span><br /><br /> <span data-ttu-id="68729-123">.NET Framework 4.5의 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="68729-123">New in the .NET Framework 4.5.</span></span>|  
|`-32BITPREF-`|<span data-ttu-id="68729-124">32BITPREFERRED 플래그를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="68729-124">Clears the 32BITPREFERRED flag.</span></span><br /><br /> <span data-ttu-id="68729-125">.NET Framework 4.5의 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="68729-125">New in the .NET Framework 4.5.</span></span>|  
|`-?`|<span data-ttu-id="68729-126">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="68729-126">Displays command syntax and options for the tool.</span></span>|  
|`-Force`|<span data-ttu-id="68729-127">어셈블리의 이름이 강력한 이름인 경우에도 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="68729-127">Forces an update even if the assembly is strong-named.</span></span> <span data-ttu-id="68729-128">**중요:**  강력한 이름의 어셈블리를 업데이트하면 코드를 실행하기 전에 다시 서명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68729-128">**Important:**  If you update a strong-named assembly, you must sign it again before executing its code.</span></span>|  
|`-help`|<span data-ttu-id="68729-129">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="68729-129">Displays command syntax and options for the tool.</span></span>|  
|`-ILONLY+`|<span data-ttu-id="68729-130">ILONLY 플래그를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="68729-130">Sets the ILONLY flag.</span></span>|  
|`-ILONLY-`|<span data-ttu-id="68729-131">ILONLY 플래그를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="68729-131">Clears the ILONLY flag.</span></span>|  
|`-nologo`|<span data-ttu-id="68729-132">Microsoft 시작 배너를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68729-132">Suppresses the Microsoft startup banner display.</span></span>|  
|`-RevertCLRHeader`|<span data-ttu-id="68729-133">CLR 헤더 버전을 2.0으로 되돌립니다.</span><span class="sxs-lookup"><span data-stu-id="68729-133">Reverts the CLR header version to 2.0.</span></span>|  
|`-UpgradeCLRHeader`|<span data-ttu-id="68729-134">CLR 헤더 버전을 2.5로 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="68729-134">Upgrades the CLR header version to 2.5.</span></span> <span data-ttu-id="68729-135">**참고:**  기본적으로 어셈블리를 실행하려면 CLR 헤더 버전이 2.5 이상이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68729-135">**Note:**  Assemblies must have a CLR header version of 2.5 or greater to run natively.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68729-136">설명</span><span class="sxs-lookup"><span data-stu-id="68729-136">Remarks</span></span>  

 <span data-ttu-id="68729-137">옵션을 지정하지 않으면 CorFlags 변환 도구에서 지정한 어셈블리에 대한 플래그를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="68729-137">If no options are specified, the CorFlags Conversion tool displays the flags for the specified assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68729-138">참조</span><span class="sxs-lookup"><span data-stu-id="68729-138">See also</span></span>

- [<span data-ttu-id="68729-139">도구</span><span class="sxs-lookup"><span data-stu-id="68729-139">Tools</span></span>](index.md)
- [<span data-ttu-id="68729-140">64비트 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="68729-140">64-bit Applications</span></span>](../64-bit-apps.md)
- [<span data-ttu-id="68729-141">개발자 명령줄 셸</span><span class="sxs-lookup"><span data-stu-id="68729-141">Developer command-line shells</span></span>](/visualstudio/ide/reference/command-prompt-powershell)
