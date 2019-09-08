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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 49e7b73559e8def890f8df8f596fbe8ad5bb5d3b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777484"
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="c4b8c-102">AssemblyOptions 열거형</span><span class="sxs-lookup"><span data-stu-id="c4b8c-102">AssemblyOptions Enumeration</span></span>
<span data-ttu-id="c4b8c-103">어셈블리 옵션을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-103">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4b8c-104">구문</span><span class="sxs-lookup"><span data-stu-id="c4b8c-104">Syntax</span></span>  
  
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
  
## <a name="fields"></a><span data-ttu-id="c4b8c-105">필드</span><span class="sxs-lookup"><span data-stu-id="c4b8c-105">Fields</span></span>  
  
|<span data-ttu-id="c4b8c-106">필드</span><span class="sxs-lookup"><span data-stu-id="c4b8c-106">Field</span></span>|<span data-ttu-id="c4b8c-107">Description</span><span class="sxs-lookup"><span data-stu-id="c4b8c-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c4b8c-108">optAssemTitle</span><span class="sxs-lookup"><span data-stu-id="c4b8c-108">optAssemTitle</span></span>|<span data-ttu-id="c4b8c-109">String-어셈블리 제목을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-109">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="c4b8c-110">optAssemDescription</span><span class="sxs-lookup"><span data-stu-id="c4b8c-110">optAssemDescription</span></span>|<span data-ttu-id="c4b8c-111">String-어셈블리 설명을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-111">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="c4b8c-112">optAssemConfig</span><span class="sxs-lookup"><span data-stu-id="c4b8c-112">optAssemConfig</span></span>|<span data-ttu-id="c4b8c-113">String-어셈블리 구성을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-113">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="c4b8c-114">optAssemOS</span><span class="sxs-lookup"><span data-stu-id="c4b8c-114">optAssemOS</span></span>|<span data-ttu-id="c4b8c-115">문자열 인코딩: "dwOSPlatformId. DwosdwOSMinorVersion".</span><span class="sxs-lookup"><span data-stu-id="c4b8c-115">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="c4b8c-116">optAssemProcessor</span><span class="sxs-lookup"><span data-stu-id="c4b8c-116">optAssemProcessor</span></span>|<span data-ttu-id="c4b8c-117">ULONG</span><span class="sxs-lookup"><span data-stu-id="c4b8c-117">ULONG</span></span>|  
|<span data-ttu-id="c4b8c-118">optAssemLocale</span><span class="sxs-lookup"><span data-stu-id="c4b8c-118">optAssemLocale</span></span>|<span data-ttu-id="c4b8c-119">String-어셈블리 로캘을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-119">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="c4b8c-120">optAssemVersion</span><span class="sxs-lookup"><span data-stu-id="c4b8c-120">optAssemVersion</span></span>|<span data-ttu-id="c4b8c-121">문자열 인코딩: "Major.Minor.Build.Revision".</span><span class="sxs-lookup"><span data-stu-id="c4b8c-121">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="c4b8c-122">optAssemCompany</span><span class="sxs-lookup"><span data-stu-id="c4b8c-122">optAssemCompany</span></span>|<span data-ttu-id="c4b8c-123">String-회사를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-123">String - Contains the company.</span></span>|  
|<span data-ttu-id="c4b8c-124">optAssemProduct</span><span class="sxs-lookup"><span data-stu-id="c4b8c-124">optAssemProduct</span></span>|<span data-ttu-id="c4b8c-125">String-제품 이름을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-125">String - Contains the product name.</span></span>|  
|<span data-ttu-id="c4b8c-126">optAssemProductVersion</span><span class="sxs-lookup"><span data-stu-id="c4b8c-126">optAssemProductVersion</span></span>|<span data-ttu-id="c4b8c-127">문자열 (InformationalVersion이 라고도 함)</span><span class="sxs-lookup"><span data-stu-id="c4b8c-127">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="c4b8c-128">optAssemCopyright</span><span class="sxs-lookup"><span data-stu-id="c4b8c-128">optAssemCopyright</span></span>|<span data-ttu-id="c4b8c-129">String-저작권 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-129">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="c4b8c-130">optAssemTrademark</span><span class="sxs-lookup"><span data-stu-id="c4b8c-130">optAssemTrademark</span></span>|<span data-ttu-id="c4b8c-131">String-상표 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-131">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="c4b8c-132">optAssemKeyFile</span><span class="sxs-lookup"><span data-stu-id="c4b8c-132">optAssemKeyFile</span></span>|<span data-ttu-id="c4b8c-133">문자열 (파일 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-133">String (file name).</span></span>|  
|<span data-ttu-id="c4b8c-134">optAssemKeyName</span><span class="sxs-lookup"><span data-stu-id="c4b8c-134">optAssemKeyName</span></span>|<span data-ttu-id="c4b8c-135">문자열 (키 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-135">String (The key name).</span></span>|  
|<span data-ttu-id="c4b8c-136">optAssemAlgID</span><span class="sxs-lookup"><span data-stu-id="c4b8c-136">optAssemAlgID</span></span>|<span data-ttu-id="c4b8c-137">ULONG</span><span class="sxs-lookup"><span data-stu-id="c4b8c-137">ULONG</span></span>|  
|<span data-ttu-id="c4b8c-138">optAssemFlags</span><span class="sxs-lookup"><span data-stu-id="c4b8c-138">optAssemFlags</span></span>|<span data-ttu-id="c4b8c-139">ULONG</span><span class="sxs-lookup"><span data-stu-id="c4b8c-139">ULONG</span></span>|  
|<span data-ttu-id="c4b8c-140">optAssemHalfSign</span><span class="sxs-lookup"><span data-stu-id="c4b8c-140">optAssemHalfSign</span></span>|<span data-ttu-id="c4b8c-141">Bool (DelaySign 라고도 함).</span><span class="sxs-lookup"><span data-stu-id="c4b8c-141">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="c4b8c-142">optAssemFileVersion</span><span class="sxs-lookup"><span data-stu-id="c4b8c-142">optAssemFileVersion</span></span>|<span data-ttu-id="c4b8c-143">"Major. ProductVersion"로 인코딩된 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="c4b8c-144">optAssemSatelliteVer</span><span class="sxs-lookup"><span data-stu-id="c4b8c-144">optAssemSatelliteVer</span></span>|<span data-ttu-id="c4b8c-145">"Major. 부. 빌드. 수정 버전"으로 문자열 인코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-145">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="c4b8c-146">optLastAssemOption</span><span class="sxs-lookup"><span data-stu-id="c4b8c-146">optLastAssemOption</span></span>|<span data-ttu-id="c4b8c-147">요소 수의 카운터입니다.</span><span class="sxs-lookup"><span data-stu-id="c4b8c-147">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c4b8c-148">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c4b8c-148">Requirements</span></span>  
 <span data-ttu-id="c4b8c-149">**헤더:** alink. h</span><span class="sxs-lookup"><span data-stu-id="c4b8c-149">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="c4b8c-150">**라이브러리**: alink .dll</span><span class="sxs-lookup"><span data-stu-id="c4b8c-150">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4b8c-151">참고자료</span><span class="sxs-lookup"><span data-stu-id="c4b8c-151">See also</span></span>

- [<span data-ttu-id="c4b8c-152">Al.exe(어셈블리 링커)</span><span class="sxs-lookup"><span data-stu-id="c4b8c-152">Al.exe (Assembly Linker)</span></span>](../../tools/al-exe-assembly-linker.md)
