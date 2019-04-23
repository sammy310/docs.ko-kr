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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 373ff0470e2403f91534df0c0ffe4039dbb0f832
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59112634"
---
# <a name="imetadataassemblyimport-interface"></a><span data-ttu-id="384f1-102">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="384f1-102">IMetaDataAssemblyImport Interface</span></span>
<span data-ttu-id="384f1-103">어셈블리 매니페스트에 액세스하여 이를 검사하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="384f1-103">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="384f1-104">메서드</span><span class="sxs-lookup"><span data-stu-id="384f1-104">Methods</span></span>  
  
|<span data-ttu-id="384f1-105">메서드</span><span class="sxs-lookup"><span data-stu-id="384f1-105">Method</span></span>|<span data-ttu-id="384f1-106">설명</span><span class="sxs-lookup"><span data-stu-id="384f1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="384f1-107">CloseEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="384f1-107">CloseEnum Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|<span data-ttu-id="384f1-108">지정한 열거자에 대 한 핸들을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="384f1-108">Releases the handle to the specified enumerator.</span></span>|  
|[<span data-ttu-id="384f1-109">EnumAssemblyRefs 메서드</span><span class="sxs-lookup"><span data-stu-id="384f1-109">EnumAssemblyRefs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|<span data-ttu-id="384f1-110">인터페이스 포인터를 포함 하는 열거자를 가져옵니다는 `mdAssemblyRef` 현재 메타 데이터 범위에 있는 어셈블리에서 참조 하는 어셈블리의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="384f1-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="384f1-111">EnumExportedTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="384f1-111">EnumExportedTypes Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|<span data-ttu-id="384f1-112">인터페이스 포인터를 포함 하는 열거자를 가져옵니다는 `mdExportedType` 현재 메타 데이터 범위에 있는 어셈블리에서 참조 되는 COM 형식의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="384f1-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="384f1-113">EnumFiles 메서드</span><span class="sxs-lookup"><span data-stu-id="384f1-113">EnumFiles Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|<span data-ttu-id="384f1-114">인터페이스 포인터를 포함 하는 열거자를 가져옵니다는 `mdFile` 현재 메타 데이터 범위에 있는 어셈블리에서 참조 되는 파일의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="384f1-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="384f1-115">EnumManifestResources 메서드</span><span class="sxs-lookup"><span data-stu-id="384f1-115">EnumManifestResources Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|<span data-ttu-id="384f1-116">인터페이스 포인터를 포함 하는 열거자를 가져옵니다는 `mdManifestResource` 현재 메타 데이터 범위에 있는 어셈블리에서 참조 되는 리소스의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="384f1-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="384f1-117">FindAssembliesByName 메서드</span><span class="sxs-lookup"><span data-stu-id="384f1-117">FindAssembliesByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|<span data-ttu-id="384f1-118">배열을 가져옵니다 `mdAssemblyRef` 지정한 이름 가진 어셈블리에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="384f1-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span></span>|  
|[<span data-ttu-id="384f1-119">FindExportedTypeByName 메서드</span><span class="sxs-lookup"><span data-stu-id="384f1-119">FindExportedTypeByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|<span data-ttu-id="384f1-120">가져옵니다는 `mdExportedType` 지정 된 이름 사용 하 여 COM 형식에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="384f1-120">Gets an `mdExportedType` token for the COM type with the specified name.</span></span>|  
|[<span data-ttu-id="384f1-121">FindManifestResourceByName 메서드</span><span class="sxs-lookup"><span data-stu-id="384f1-121">FindManifestResourceByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|<span data-ttu-id="384f1-122">가져옵니다는 `mdManifestResource` 지정 된 이름의 리소스에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="384f1-122">Gets an `mdManifestResource` token for the resource with the specified name.</span></span>|  
|[<span data-ttu-id="384f1-123">GetAssemblyFromScope 메서드</span><span class="sxs-lookup"><span data-stu-id="384f1-123">GetAssemblyFromScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|<span data-ttu-id="384f1-124">현재 메타 데이터 범위에서 어셈블리에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="384f1-124">Gets the token for the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="384f1-125">GetAssemblyProps 메서드</span><span class="sxs-lookup"><span data-stu-id="384f1-125">GetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|<span data-ttu-id="384f1-126">지정된 된 어셈블리의 속성 설정을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="384f1-126">Gets the property settings of the specified assembly.</span></span>|  
|[<span data-ttu-id="384f1-127">GetAssemblyRefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="384f1-127">GetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|<span data-ttu-id="384f1-128">지정 된 속성 설정을 가져옵니다 `mdAssemblyRef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="384f1-128">Gets the property settings of the specified `mdAssemblyRef` token.</span></span>|  
|[<span data-ttu-id="384f1-129">GetExportedTypeProps 메서드</span><span class="sxs-lookup"><span data-stu-id="384f1-129">GetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|<span data-ttu-id="384f1-130">지정 된 COM 형식의 속성 설정을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="384f1-130">Gets the property settings of the specified COM type.</span></span>|  
|[<span data-ttu-id="384f1-131">GetFileProps 메서드</span><span class="sxs-lookup"><span data-stu-id="384f1-131">GetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|<span data-ttu-id="384f1-132">지정된 된 파일의 속성 설정을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="384f1-132">Gets the property settings of the specified file.</span></span>|  
|[<span data-ttu-id="384f1-133">GetManifestResourceProps 메서드</span><span class="sxs-lookup"><span data-stu-id="384f1-133">GetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|<span data-ttu-id="384f1-134">지정된 된 매니페스트 리소스의 속성 설정을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="384f1-134">Gets the property settings of the specified manifest resource.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="384f1-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="384f1-135">Requirements</span></span>  
 <span data-ttu-id="384f1-136">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="384f1-136">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="384f1-137">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="384f1-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="384f1-138">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="384f1-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="384f1-139">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="384f1-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="384f1-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="384f1-140">See also</span></span>

- [<span data-ttu-id="384f1-141">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="384f1-141">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="384f1-142">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="384f1-142">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
