---
title: AssemblyOptions 열거형
ms.date: 03/30/2017
api_name:
- AssemblyOptions
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyOptions
helpviewer_keywords:
- Alink API, AssemblyOptions enumeration
- AssemblyOptions enumeration
ms.assetid: 84f83921-64cb-49e3-ac8b-22a0b77b18a8
topic_type:
- apiref
ms.openlocfilehash: 352e1acd1fdd8297754e18b2e8c6448ea723a557
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717033"
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="5c90f-102">AssemblyOptions 열거형</span><span class="sxs-lookup"><span data-stu-id="5c90f-102">AssemblyOptions Enumeration</span></span>

<span data-ttu-id="5c90f-103">어셈블리 옵션을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90f-103">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c90f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5c90f-104">Syntax</span></span>  
  
```cpp  
typedef enum _AssemblyOptions {  
    optAssemTitle = 0,  
    optAssemDescription,  
    optAssemConfig,  
    optAssemOS,  
    optAssemProcessor,  
    optAssemLocale,  
    optAssemVersion,  
    optAssemCompany,  
    optAssemProduct,  
    optAssemProductVersion,  
    optAssemCopyright,  
    optAssemTrademark,  
    optAssemKeyFile,  
    optAssemKeyName,  
    optAssemAlgID,  
    optAssemFlags,  
    optAssemHalfSign,  
    optAssemFileVersion,  
    optAssemSatelliteVer,  
    optLastAssemOption  
}   AssemblyOptions;  
```  
  
## <a name="fields"></a><span data-ttu-id="5c90f-105">필드</span><span class="sxs-lookup"><span data-stu-id="5c90f-105">Fields</span></span>  
  
|<span data-ttu-id="5c90f-106">필드</span><span class="sxs-lookup"><span data-stu-id="5c90f-106">Field</span></span>|<span data-ttu-id="5c90f-107">설명</span><span class="sxs-lookup"><span data-stu-id="5c90f-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5c90f-108">optAssemTitle</span><span class="sxs-lookup"><span data-stu-id="5c90f-108">optAssemTitle</span></span>|<span data-ttu-id="5c90f-109">String-어셈블리 제목을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5c90f-109">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="5c90f-110">optAssemDescription</span><span class="sxs-lookup"><span data-stu-id="5c90f-110">optAssemDescription</span></span>|<span data-ttu-id="5c90f-111">String-어셈블리 설명을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90f-111">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="5c90f-112">optAssemConfig</span><span class="sxs-lookup"><span data-stu-id="5c90f-112">optAssemConfig</span></span>|<span data-ttu-id="5c90f-113">String-어셈블리 구성을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90f-113">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="5c90f-114">optAssemOS</span><span class="sxs-lookup"><span data-stu-id="5c90f-114">optAssemOS</span></span>|<span data-ttu-id="5c90f-115">문자열 인코딩: "dwOSPlatformId. DwosdwOSMinorVersion".</span><span class="sxs-lookup"><span data-stu-id="5c90f-115">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="5c90f-116">optAssemProcessor</span><span class="sxs-lookup"><span data-stu-id="5c90f-116">optAssemProcessor</span></span>|<span data-ttu-id="5c90f-117">ULONG</span><span class="sxs-lookup"><span data-stu-id="5c90f-117">ULONG</span></span>|  
|<span data-ttu-id="5c90f-118">optAssemLocale</span><span class="sxs-lookup"><span data-stu-id="5c90f-118">optAssemLocale</span></span>|<span data-ttu-id="5c90f-119">String-어셈블리 로캘을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90f-119">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="5c90f-120">optAssemVersion</span><span class="sxs-lookup"><span data-stu-id="5c90f-120">optAssemVersion</span></span>|<span data-ttu-id="5c90f-121">문자열 인코딩: "주. 부. 빌드. 수정 버전".</span><span class="sxs-lookup"><span data-stu-id="5c90f-121">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="5c90f-122">optAssemCompany</span><span class="sxs-lookup"><span data-stu-id="5c90f-122">optAssemCompany</span></span>|<span data-ttu-id="5c90f-123">String-회사를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90f-123">String - Contains the company.</span></span>|  
|<span data-ttu-id="5c90f-124">optAssemProduct</span><span class="sxs-lookup"><span data-stu-id="5c90f-124">optAssemProduct</span></span>|<span data-ttu-id="5c90f-125">String-제품 이름을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90f-125">String - Contains the product name.</span></span>|  
|<span data-ttu-id="5c90f-126">optAssemProductVersion</span><span class="sxs-lookup"><span data-stu-id="5c90f-126">optAssemProductVersion</span></span>|<span data-ttu-id="5c90f-127">문자열 (InformationalVersion이 라고도 함)</span><span class="sxs-lookup"><span data-stu-id="5c90f-127">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="5c90f-128">optAssemCopyright</span><span class="sxs-lookup"><span data-stu-id="5c90f-128">optAssemCopyright</span></span>|<span data-ttu-id="5c90f-129">String-저작권 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90f-129">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="5c90f-130">optAssemTrademark</span><span class="sxs-lookup"><span data-stu-id="5c90f-130">optAssemTrademark</span></span>|<span data-ttu-id="5c90f-131">String-상표 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c90f-131">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="5c90f-132">optAssemKeyFile</span><span class="sxs-lookup"><span data-stu-id="5c90f-132">optAssemKeyFile</span></span>|<span data-ttu-id="5c90f-133">문자열 (파일 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="5c90f-133">String (file name).</span></span>|  
|<span data-ttu-id="5c90f-134">optAssemKeyName</span><span class="sxs-lookup"><span data-stu-id="5c90f-134">optAssemKeyName</span></span>|<span data-ttu-id="5c90f-135">문자열 (키 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="5c90f-135">String (The key name).</span></span>|  
|<span data-ttu-id="5c90f-136">optAssemAlgID</span><span class="sxs-lookup"><span data-stu-id="5c90f-136">optAssemAlgID</span></span>|<span data-ttu-id="5c90f-137">ULONG</span><span class="sxs-lookup"><span data-stu-id="5c90f-137">ULONG</span></span>|  
|<span data-ttu-id="5c90f-138">optAssemFlags</span><span class="sxs-lookup"><span data-stu-id="5c90f-138">optAssemFlags</span></span>|<span data-ttu-id="5c90f-139">ULONG</span><span class="sxs-lookup"><span data-stu-id="5c90f-139">ULONG</span></span>|  
|<span data-ttu-id="5c90f-140">optAssemHalfSign</span><span class="sxs-lookup"><span data-stu-id="5c90f-140">optAssemHalfSign</span></span>|<span data-ttu-id="5c90f-141">Bool (DelaySign 라고도 함).</span><span class="sxs-lookup"><span data-stu-id="5c90f-141">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="5c90f-142">optAssemFileVersion</span><span class="sxs-lookup"><span data-stu-id="5c90f-142">optAssemFileVersion</span></span>|<span data-ttu-id="5c90f-143">"Major. ProductVersion"로 인코딩된 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5c90f-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="5c90f-144">optAssemSatelliteVer</span><span class="sxs-lookup"><span data-stu-id="5c90f-144">optAssemSatelliteVer</span></span>|<span data-ttu-id="5c90f-145">"Major. 부. 빌드. 수정 버전"으로 문자열 인코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c90f-145">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="5c90f-146">optLastAssemOption</span><span class="sxs-lookup"><span data-stu-id="5c90f-146">optLastAssemOption</span></span>|<span data-ttu-id="5c90f-147">요소 수의 카운터입니다.</span><span class="sxs-lookup"><span data-stu-id="5c90f-147">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5c90f-148">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5c90f-148">Requirements</span></span>  

 <span data-ttu-id="5c90f-149">**헤더:** alink. h</span><span class="sxs-lookup"><span data-stu-id="5c90f-149">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="5c90f-150">**라이브러리**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="5c90f-150">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c90f-151">참조</span><span class="sxs-lookup"><span data-stu-id="5c90f-151">See also</span></span>

- [<span data-ttu-id="5c90f-152">Al.exe(어셈블리 링커)</span><span class="sxs-lookup"><span data-stu-id="5c90f-152">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
