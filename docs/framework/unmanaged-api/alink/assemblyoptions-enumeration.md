---
description: '자세한 정보: AssemblyOptions 열거형'
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
ms.openlocfilehash: aba9ecb3176f533e2d53e2e45fef3d1dc4e55077
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638420"
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="70f28-103">AssemblyOptions 열거형</span><span class="sxs-lookup"><span data-stu-id="70f28-103">AssemblyOptions Enumeration</span></span>

<span data-ttu-id="70f28-104">어셈블리 옵션을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="70f28-104">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70f28-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="70f28-105">Syntax</span></span>  
  
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
  
## <a name="fields"></a><span data-ttu-id="70f28-106">필드</span><span class="sxs-lookup"><span data-stu-id="70f28-106">Fields</span></span>  
  
|<span data-ttu-id="70f28-107">필드</span><span class="sxs-lookup"><span data-stu-id="70f28-107">Field</span></span>|<span data-ttu-id="70f28-108">설명</span><span class="sxs-lookup"><span data-stu-id="70f28-108">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="70f28-109">optAssemTitle</span><span class="sxs-lookup"><span data-stu-id="70f28-109">optAssemTitle</span></span>|<span data-ttu-id="70f28-110">String-어셈블리 제목을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="70f28-110">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="70f28-111">optAssemDescription</span><span class="sxs-lookup"><span data-stu-id="70f28-111">optAssemDescription</span></span>|<span data-ttu-id="70f28-112">String-어셈블리 설명을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="70f28-112">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="70f28-113">optAssemConfig</span><span class="sxs-lookup"><span data-stu-id="70f28-113">optAssemConfig</span></span>|<span data-ttu-id="70f28-114">String-어셈블리 구성을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="70f28-114">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="70f28-115">optAssemOS</span><span class="sxs-lookup"><span data-stu-id="70f28-115">optAssemOS</span></span>|<span data-ttu-id="70f28-116">문자열 인코딩: "dwOSPlatformId. DwosdwOSMinorVersion".</span><span class="sxs-lookup"><span data-stu-id="70f28-116">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="70f28-117">optAssemProcessor</span><span class="sxs-lookup"><span data-stu-id="70f28-117">optAssemProcessor</span></span>|<span data-ttu-id="70f28-118">ULONG</span><span class="sxs-lookup"><span data-stu-id="70f28-118">ULONG</span></span>|  
|<span data-ttu-id="70f28-119">optAssemLocale</span><span class="sxs-lookup"><span data-stu-id="70f28-119">optAssemLocale</span></span>|<span data-ttu-id="70f28-120">String-어셈블리 로캘을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="70f28-120">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="70f28-121">optAssemVersion</span><span class="sxs-lookup"><span data-stu-id="70f28-121">optAssemVersion</span></span>|<span data-ttu-id="70f28-122">문자열 인코딩: "주. 부. 빌드. 수정 버전".</span><span class="sxs-lookup"><span data-stu-id="70f28-122">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="70f28-123">optAssemCompany</span><span class="sxs-lookup"><span data-stu-id="70f28-123">optAssemCompany</span></span>|<span data-ttu-id="70f28-124">String-회사를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="70f28-124">String - Contains the company.</span></span>|  
|<span data-ttu-id="70f28-125">optAssemProduct</span><span class="sxs-lookup"><span data-stu-id="70f28-125">optAssemProduct</span></span>|<span data-ttu-id="70f28-126">String-제품 이름을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="70f28-126">String - Contains the product name.</span></span>|  
|<span data-ttu-id="70f28-127">optAssemProductVersion</span><span class="sxs-lookup"><span data-stu-id="70f28-127">optAssemProductVersion</span></span>|<span data-ttu-id="70f28-128">문자열 (InformationalVersion이 라고도 함)</span><span class="sxs-lookup"><span data-stu-id="70f28-128">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="70f28-129">optAssemCopyright</span><span class="sxs-lookup"><span data-stu-id="70f28-129">optAssemCopyright</span></span>|<span data-ttu-id="70f28-130">String-저작권 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="70f28-130">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="70f28-131">optAssemTrademark</span><span class="sxs-lookup"><span data-stu-id="70f28-131">optAssemTrademark</span></span>|<span data-ttu-id="70f28-132">String-상표 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="70f28-132">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="70f28-133">optAssemKeyFile</span><span class="sxs-lookup"><span data-stu-id="70f28-133">optAssemKeyFile</span></span>|<span data-ttu-id="70f28-134">문자열 (파일 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="70f28-134">String (file name).</span></span>|  
|<span data-ttu-id="70f28-135">optAssemKeyName</span><span class="sxs-lookup"><span data-stu-id="70f28-135">optAssemKeyName</span></span>|<span data-ttu-id="70f28-136">문자열 (키 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="70f28-136">String (The key name).</span></span>|  
|<span data-ttu-id="70f28-137">optAssemAlgID</span><span class="sxs-lookup"><span data-stu-id="70f28-137">optAssemAlgID</span></span>|<span data-ttu-id="70f28-138">ULONG</span><span class="sxs-lookup"><span data-stu-id="70f28-138">ULONG</span></span>|  
|<span data-ttu-id="70f28-139">optAssemFlags</span><span class="sxs-lookup"><span data-stu-id="70f28-139">optAssemFlags</span></span>|<span data-ttu-id="70f28-140">ULONG</span><span class="sxs-lookup"><span data-stu-id="70f28-140">ULONG</span></span>|  
|<span data-ttu-id="70f28-141">optAssemHalfSign</span><span class="sxs-lookup"><span data-stu-id="70f28-141">optAssemHalfSign</span></span>|<span data-ttu-id="70f28-142">Bool (DelaySign 라고도 함).</span><span class="sxs-lookup"><span data-stu-id="70f28-142">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="70f28-143">optAssemFileVersion</span><span class="sxs-lookup"><span data-stu-id="70f28-143">optAssemFileVersion</span></span>|<span data-ttu-id="70f28-144">"Major. ProductVersion"로 인코딩된 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="70f28-144">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="70f28-145">optAssemSatelliteVer</span><span class="sxs-lookup"><span data-stu-id="70f28-145">optAssemSatelliteVer</span></span>|<span data-ttu-id="70f28-146">"Major. 부. 빌드. 수정 버전"으로 문자열 인코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="70f28-146">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="70f28-147">optLastAssemOption</span><span class="sxs-lookup"><span data-stu-id="70f28-147">optLastAssemOption</span></span>|<span data-ttu-id="70f28-148">요소 수의 카운터입니다.</span><span class="sxs-lookup"><span data-stu-id="70f28-148">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="70f28-149">요구 사항</span><span class="sxs-lookup"><span data-stu-id="70f28-149">Requirements</span></span>  

 <span data-ttu-id="70f28-150">**헤더:** alink. h</span><span class="sxs-lookup"><span data-stu-id="70f28-150">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="70f28-151">**라이브러리**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="70f28-151">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70f28-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="70f28-152">See also</span></span>

- [<span data-ttu-id="70f28-153">Al.exe(어셈블리 링커)</span><span class="sxs-lookup"><span data-stu-id="70f28-153">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
