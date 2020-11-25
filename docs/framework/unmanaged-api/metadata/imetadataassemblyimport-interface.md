---
title: IMetaDataAssemblyImport 인터페이스
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport
helpviewer_keywords:
- IMetaDataAssemblyImport interface [.NET Framework metadata]
ms.assetid: 29c6fba5-4cea-417d-b484-7ed22ebff1c9
topic_type:
- apiref
ms.openlocfilehash: c556fe247754b363ece0c5dc60750068276ddcc4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714759"
---
# <a name="imetadataassemblyimport-interface"></a><span data-ttu-id="0f3ce-102">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0f3ce-102">IMetaDataAssemblyImport Interface</span></span>

<span data-ttu-id="0f3ce-103">어셈블리 매니페스트에 액세스하여 이를 검사하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0f3ce-103">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0f3ce-104">메서드</span><span class="sxs-lookup"><span data-stu-id="0f3ce-104">Methods</span></span>  
  
|<span data-ttu-id="0f3ce-105">메서드</span><span class="sxs-lookup"><span data-stu-id="0f3ce-105">Method</span></span>|<span data-ttu-id="0f3ce-106">설명</span><span class="sxs-lookup"><span data-stu-id="0f3ce-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0f3ce-107">CloseEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="0f3ce-107">CloseEnum Method</span></span>](imetadataassemblyimport-closeenum-method.md)|<span data-ttu-id="0f3ce-108">지정 된 열거자에 대 한 핸들을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f3ce-108">Releases the handle to the specified enumerator.</span></span>|  
|[<span data-ttu-id="0f3ce-109">EnumAssemblyRefs 메서드</span><span class="sxs-lookup"><span data-stu-id="0f3ce-109">EnumAssemblyRefs Method</span></span>](imetadataassemblyimport-enumassemblyrefs-method.md)|<span data-ttu-id="0f3ce-110">`mdAssemblyRef`현재 메타 데이터 범위에서 어셈블리가 참조 하는 어셈블리의 토큰을 포함 하는 열거자에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0f3ce-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="0f3ce-111">EnumExportedTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="0f3ce-111">EnumExportedTypes Method</span></span>](imetadataassemblyimport-enumexportedtypes-method.md)|<span data-ttu-id="0f3ce-112">`mdExportedType`현재 메타 데이터 범위에서 어셈블리가 참조 하는 COM 형식의 토큰을 포함 하는 열거자에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0f3ce-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="0f3ce-113">EnumFiles 메서드</span><span class="sxs-lookup"><span data-stu-id="0f3ce-113">EnumFiles Method</span></span>](imetadataassemblyimport-enumfiles-method.md)|<span data-ttu-id="0f3ce-114">`mdFile`현재 메타 데이터 범위에서 어셈블리가 참조 하는 파일의 토큰을 포함 하는 열거자에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0f3ce-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="0f3ce-115">EnumManifestResources 메서드</span><span class="sxs-lookup"><span data-stu-id="0f3ce-115">EnumManifestResources Method</span></span>](imetadataassemblyimport-enummanifestresources-method.md)|<span data-ttu-id="0f3ce-116">`mdManifestResource`현재 메타 데이터 범위에서 어셈블리가 참조 하는 리소스의 토큰을 포함 하는 열거자에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0f3ce-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="0f3ce-117">FindAssembliesByName 메서드</span><span class="sxs-lookup"><span data-stu-id="0f3ce-117">FindAssembliesByName Method</span></span>](imetadataassemblyimport-findassembliesbyname-method.md)|<span data-ttu-id="0f3ce-118">`mdAssemblyRef`지정 된 이름을 가진 어셈블리에 대 한 토큰의 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0f3ce-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span></span>|  
|[<span data-ttu-id="0f3ce-119">FindExportedTypeByName 메서드</span><span class="sxs-lookup"><span data-stu-id="0f3ce-119">FindExportedTypeByName Method</span></span>](imetadataassemblyimport-findexportedtypebyname-method.md)|<span data-ttu-id="0f3ce-120">지정 된 `mdExportedType` 이름을 사용 하 여 COM 형식에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0f3ce-120">Gets an `mdExportedType` token for the COM type with the specified name.</span></span>|  
|[<span data-ttu-id="0f3ce-121">FindManifestResourceByName 메서드</span><span class="sxs-lookup"><span data-stu-id="0f3ce-121">FindManifestResourceByName Method</span></span>](imetadataassemblyimport-findmanifestresourcebyname-method.md)|<span data-ttu-id="0f3ce-122">지정 된 `mdManifestResource` 이름의 리소스에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0f3ce-122">Gets an `mdManifestResource` token for the resource with the specified name.</span></span>|  
|[<span data-ttu-id="0f3ce-123">GetAssemblyFromScope 메서드</span><span class="sxs-lookup"><span data-stu-id="0f3ce-123">GetAssemblyFromScope Method</span></span>](imetadataassemblyimport-getassemblyfromscope-method.md)|<span data-ttu-id="0f3ce-124">현재 메타 데이터 범위에 있는 어셈블리에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0f3ce-124">Gets the token for the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="0f3ce-125">GetAssemblyProps 메서드</span><span class="sxs-lookup"><span data-stu-id="0f3ce-125">GetAssemblyProps Method</span></span>](imetadataassemblyimport-getassemblyprops-method.md)|<span data-ttu-id="0f3ce-126">지정 된 어셈블리의 속성 설정을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0f3ce-126">Gets the property settings of the specified assembly.</span></span>|  
|[<span data-ttu-id="0f3ce-127">GetAssemblyRefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="0f3ce-127">GetAssemblyRefProps Method</span></span>](imetadataassemblyimport-getassemblyrefprops-method.md)|<span data-ttu-id="0f3ce-128">지정 된 토큰의 속성 설정을 가져옵니다 `mdAssemblyRef` .</span><span class="sxs-lookup"><span data-stu-id="0f3ce-128">Gets the property settings of the specified `mdAssemblyRef` token.</span></span>|  
|[<span data-ttu-id="0f3ce-129">GetExportedTypeProps 메서드</span><span class="sxs-lookup"><span data-stu-id="0f3ce-129">GetExportedTypeProps Method</span></span>](imetadataassemblyimport-getexportedtypeprops-method.md)|<span data-ttu-id="0f3ce-130">지정 된 COM 형식의 속성 설정을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0f3ce-130">Gets the property settings of the specified COM type.</span></span>|  
|[<span data-ttu-id="0f3ce-131">GetFileProps 메서드</span><span class="sxs-lookup"><span data-stu-id="0f3ce-131">GetFileProps Method</span></span>](imetadataassemblyimport-getfileprops-method.md)|<span data-ttu-id="0f3ce-132">지정 된 파일의 속성 설정을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0f3ce-132">Gets the property settings of the specified file.</span></span>|  
|[<span data-ttu-id="0f3ce-133">GetManifestResourceProps 메서드</span><span class="sxs-lookup"><span data-stu-id="0f3ce-133">GetManifestResourceProps Method</span></span>](imetadataassemblyimport-getmanifestresourceprops-method.md)|<span data-ttu-id="0f3ce-134">지정 된 매니페스트 리소스의 속성 설정을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0f3ce-134">Gets the property settings of the specified manifest resource.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0f3ce-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0f3ce-135">Requirements</span></span>  

 <span data-ttu-id="0f3ce-136">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0f3ce-136">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f3ce-137">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="0f3ce-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0f3ce-138">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f3ce-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0f3ce-139">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f3ce-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f3ce-140">참조</span><span class="sxs-lookup"><span data-stu-id="0f3ce-140">See also</span></span>

- [<span data-ttu-id="0f3ce-141">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0f3ce-141">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="0f3ce-142">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0f3ce-142">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
