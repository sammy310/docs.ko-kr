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
ms.openlocfilehash: 324e30f6cbcaa1d1d81c7c03967dbb629d2cd6e9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742269"
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="2ef70-102">AssemblyOptions 열거형</span><span class="sxs-lookup"><span data-stu-id="2ef70-102">AssemblyOptions Enumeration</span></span>
<span data-ttu-id="2ef70-103">어셈블리 옵션을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef70-103">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ef70-104">구문</span><span class="sxs-lookup"><span data-stu-id="2ef70-104">Syntax</span></span>  
  
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
  
## <a name="fields"></a><span data-ttu-id="2ef70-105">필드</span><span class="sxs-lookup"><span data-stu-id="2ef70-105">Fields</span></span>  
  
|<span data-ttu-id="2ef70-106">필드</span><span class="sxs-lookup"><span data-stu-id="2ef70-106">Field</span></span>|<span data-ttu-id="2ef70-107">설명</span><span class="sxs-lookup"><span data-stu-id="2ef70-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2ef70-108">optAssemTitle</span><span class="sxs-lookup"><span data-stu-id="2ef70-108">optAssemTitle</span></span>|<span data-ttu-id="2ef70-109">문자열-어셈블리 제목을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2ef70-109">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="2ef70-110">optAssemDescription</span><span class="sxs-lookup"><span data-stu-id="2ef70-110">optAssemDescription</span></span>|<span data-ttu-id="2ef70-111">문자열-어셈블리 파일에 대 한 설명을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef70-111">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="2ef70-112">optAssemConfig</span><span class="sxs-lookup"><span data-stu-id="2ef70-112">optAssemConfig</span></span>|<span data-ttu-id="2ef70-113">문자열-어셈블리 구성을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef70-113">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="2ef70-114">optAssemOS</span><span class="sxs-lookup"><span data-stu-id="2ef70-114">optAssemOS</span></span>|<span data-ttu-id="2ef70-115">로 인코드된 문자열: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion"입니다.</span><span class="sxs-lookup"><span data-stu-id="2ef70-115">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="2ef70-116">optAssemProcessor</span><span class="sxs-lookup"><span data-stu-id="2ef70-116">optAssemProcessor</span></span>|<span data-ttu-id="2ef70-117">ULONG</span><span class="sxs-lookup"><span data-stu-id="2ef70-117">ULONG</span></span>|  
|<span data-ttu-id="2ef70-118">optAssemLocale</span><span class="sxs-lookup"><span data-stu-id="2ef70-118">optAssemLocale</span></span>|<span data-ttu-id="2ef70-119">문자열-어셈블리 로캘을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef70-119">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="2ef70-120">optAssemVersion</span><span class="sxs-lookup"><span data-stu-id="2ef70-120">optAssemVersion</span></span>|<span data-ttu-id="2ef70-121">문자열-로 인코딩됩니다. "Major.Minor.Build.Revision".</span><span class="sxs-lookup"><span data-stu-id="2ef70-121">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="2ef70-122">optAssemCompany</span><span class="sxs-lookup"><span data-stu-id="2ef70-122">optAssemCompany</span></span>|<span data-ttu-id="2ef70-123">문자열-회사 이름을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef70-123">String - Contains the company.</span></span>|  
|<span data-ttu-id="2ef70-124">optAssemProduct</span><span class="sxs-lookup"><span data-stu-id="2ef70-124">optAssemProduct</span></span>|<span data-ttu-id="2ef70-125">문자열-제품 이름을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef70-125">String - Contains the product name.</span></span>|  
|<span data-ttu-id="2ef70-126">optAssemProductVersion</span><span class="sxs-lookup"><span data-stu-id="2ef70-126">optAssemProductVersion</span></span>|<span data-ttu-id="2ef70-127">문자열 (InformationalVersion이 라고도 함)입니다.</span><span class="sxs-lookup"><span data-stu-id="2ef70-127">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="2ef70-128">optAssemCopyright</span><span class="sxs-lookup"><span data-stu-id="2ef70-128">optAssemCopyright</span></span>|<span data-ttu-id="2ef70-129">문자열-저작권 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef70-129">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="2ef70-130">optAssemTrademark</span><span class="sxs-lookup"><span data-stu-id="2ef70-130">optAssemTrademark</span></span>|<span data-ttu-id="2ef70-131">문자열-상표 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ef70-131">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="2ef70-132">optAssemKeyFile</span><span class="sxs-lookup"><span data-stu-id="2ef70-132">optAssemKeyFile</span></span>|<span data-ttu-id="2ef70-133">String (파일 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="2ef70-133">String (file name).</span></span>|  
|<span data-ttu-id="2ef70-134">optAssemKeyName</span><span class="sxs-lookup"><span data-stu-id="2ef70-134">optAssemKeyName</span></span>|<span data-ttu-id="2ef70-135">문자열 (키 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="2ef70-135">String (The key name).</span></span>|  
|<span data-ttu-id="2ef70-136">optAssemAlgID</span><span class="sxs-lookup"><span data-stu-id="2ef70-136">optAssemAlgID</span></span>|<span data-ttu-id="2ef70-137">ULONG</span><span class="sxs-lookup"><span data-stu-id="2ef70-137">ULONG</span></span>|  
|<span data-ttu-id="2ef70-138">optAssemFlags</span><span class="sxs-lookup"><span data-stu-id="2ef70-138">optAssemFlags</span></span>|<span data-ttu-id="2ef70-139">ULONG</span><span class="sxs-lookup"><span data-stu-id="2ef70-139">ULONG</span></span>|  
|<span data-ttu-id="2ef70-140">optAssemHalfSign</span><span class="sxs-lookup"><span data-stu-id="2ef70-140">optAssemHalfSign</span></span>|<span data-ttu-id="2ef70-141">Bool (DelaySign 라고도 함)입니다.</span><span class="sxs-lookup"><span data-stu-id="2ef70-141">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="2ef70-142">optAssemFileVersion</span><span class="sxs-lookup"><span data-stu-id="2ef70-142">optAssemFileVersion</span></span>|<span data-ttu-id="2ef70-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span><span class="sxs-lookup"><span data-stu-id="2ef70-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="2ef70-144">optAssemSatelliteVer</span><span class="sxs-lookup"><span data-stu-id="2ef70-144">optAssemSatelliteVer</span></span>|<span data-ttu-id="2ef70-145">문자열-"Major.Minor.Build.Revision"로 인코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ef70-145">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="2ef70-146">optLastAssemOption</span><span class="sxs-lookup"><span data-stu-id="2ef70-146">optLastAssemOption</span></span>|<span data-ttu-id="2ef70-147">요소 수가 카운터입니다.</span><span class="sxs-lookup"><span data-stu-id="2ef70-147">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2ef70-148">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2ef70-148">Requirements</span></span>  
 <span data-ttu-id="2ef70-149">**헤더:** alink.h</span><span class="sxs-lookup"><span data-stu-id="2ef70-149">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="2ef70-150">**라이브러리**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="2ef70-150">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ef70-151">참고자료</span><span class="sxs-lookup"><span data-stu-id="2ef70-151">See also</span></span>

- [<span data-ttu-id="2ef70-152">Al.exe(어셈블리 링커)</span><span class="sxs-lookup"><span data-stu-id="2ef70-152">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
