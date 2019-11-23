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
ms.openlocfilehash: 289e26868ff2eb9e1d97cf084e9a888815062ea4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436311"
---
# <a name="imetadataassemblyimport-interface"></a><span data-ttu-id="5a466-102">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a466-102">IMetaDataAssemblyImport Interface</span></span>
<span data-ttu-id="5a466-103">어셈블리 매니페스트에 액세스하여 이를 검사하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5a466-103">Provides methods to access and examine the contents of an assembly manifest.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5a466-104">메서드</span><span class="sxs-lookup"><span data-stu-id="5a466-104">Methods</span></span>  
  
|<span data-ttu-id="5a466-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5a466-105">Method</span></span>|<span data-ttu-id="5a466-106">설명</span><span class="sxs-lookup"><span data-stu-id="5a466-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5a466-107">CloseEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="5a466-107">CloseEnum Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|<span data-ttu-id="5a466-108">Releases the handle to the specified enumerator.</span><span class="sxs-lookup"><span data-stu-id="5a466-108">Releases the handle to the specified enumerator.</span></span>|  
|[<span data-ttu-id="5a466-109">EnumAssemblyRefs 메서드</span><span class="sxs-lookup"><span data-stu-id="5a466-109">EnumAssemblyRefs Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|<span data-ttu-id="5a466-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span><span class="sxs-lookup"><span data-stu-id="5a466-110">Gets an interface pointer to an enumerator that contains the `mdAssemblyRef` tokens of the assemblies referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="5a466-111">EnumExportedTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="5a466-111">EnumExportedTypes Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|<span data-ttu-id="5a466-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span><span class="sxs-lookup"><span data-stu-id="5a466-112">Gets an interface pointer to an enumerator that contains the `mdExportedType` tokens of the COM types referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="5a466-113">EnumFiles 메서드</span><span class="sxs-lookup"><span data-stu-id="5a466-113">EnumFiles Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|<span data-ttu-id="5a466-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span><span class="sxs-lookup"><span data-stu-id="5a466-114">Gets an interface pointer to an enumerator that contains the `mdFile` tokens of the files referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="5a466-115">EnumManifestResources 메서드</span><span class="sxs-lookup"><span data-stu-id="5a466-115">EnumManifestResources Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|<span data-ttu-id="5a466-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span><span class="sxs-lookup"><span data-stu-id="5a466-116">Gets an interface pointer to an enumerator that contains the `mdManifestResource` tokens of the resources referenced by the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="5a466-117">FindAssembliesByName 메서드</span><span class="sxs-lookup"><span data-stu-id="5a466-117">FindAssembliesByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|<span data-ttu-id="5a466-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span><span class="sxs-lookup"><span data-stu-id="5a466-118">Gets an array of `mdAssemblyRef` tokens for the assemblies with the specified name.</span></span>|  
|[<span data-ttu-id="5a466-119">FindExportedTypeByName 메서드</span><span class="sxs-lookup"><span data-stu-id="5a466-119">FindExportedTypeByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|<span data-ttu-id="5a466-120">Gets an `mdExportedType` token for the COM type with the specified name.</span><span class="sxs-lookup"><span data-stu-id="5a466-120">Gets an `mdExportedType` token for the COM type with the specified name.</span></span>|  
|[<span data-ttu-id="5a466-121">FindManifestResourceByName 메서드</span><span class="sxs-lookup"><span data-stu-id="5a466-121">FindManifestResourceByName Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|<span data-ttu-id="5a466-122">Gets an `mdManifestResource` token for the resource with the specified name.</span><span class="sxs-lookup"><span data-stu-id="5a466-122">Gets an `mdManifestResource` token for the resource with the specified name.</span></span>|  
|[<span data-ttu-id="5a466-123">GetAssemblyFromScope 메서드</span><span class="sxs-lookup"><span data-stu-id="5a466-123">GetAssemblyFromScope Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|<span data-ttu-id="5a466-124">Gets the token for the assembly in the current metadata scope.</span><span class="sxs-lookup"><span data-stu-id="5a466-124">Gets the token for the assembly in the current metadata scope.</span></span>|  
|[<span data-ttu-id="5a466-125">GetAssemblyProps 메서드</span><span class="sxs-lookup"><span data-stu-id="5a466-125">GetAssemblyProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|<span data-ttu-id="5a466-126">Gets the property settings of the specified assembly.</span><span class="sxs-lookup"><span data-stu-id="5a466-126">Gets the property settings of the specified assembly.</span></span>|  
|[<span data-ttu-id="5a466-127">GetAssemblyRefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="5a466-127">GetAssemblyRefProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|<span data-ttu-id="5a466-128">Gets the property settings of the specified `mdAssemblyRef` token.</span><span class="sxs-lookup"><span data-stu-id="5a466-128">Gets the property settings of the specified `mdAssemblyRef` token.</span></span>|  
|[<span data-ttu-id="5a466-129">GetExportedTypeProps 메서드</span><span class="sxs-lookup"><span data-stu-id="5a466-129">GetExportedTypeProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|<span data-ttu-id="5a466-130">Gets the property settings of the specified COM type.</span><span class="sxs-lookup"><span data-stu-id="5a466-130">Gets the property settings of the specified COM type.</span></span>|  
|[<span data-ttu-id="5a466-131">GetFileProps 메서드</span><span class="sxs-lookup"><span data-stu-id="5a466-131">GetFileProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|<span data-ttu-id="5a466-132">Gets the property settings of the specified file.</span><span class="sxs-lookup"><span data-stu-id="5a466-132">Gets the property settings of the specified file.</span></span>|  
|[<span data-ttu-id="5a466-133">GetManifestResourceProps 메서드</span><span class="sxs-lookup"><span data-stu-id="5a466-133">GetManifestResourceProps Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|<span data-ttu-id="5a466-134">Gets the property settings of the specified manifest resource.</span><span class="sxs-lookup"><span data-stu-id="5a466-134">Gets the property settings of the specified manifest resource.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5a466-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5a466-135">Requirements</span></span>  
 <span data-ttu-id="5a466-136">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a466-136">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a466-137">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5a466-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5a466-138">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5a466-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5a466-139">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a466-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a466-140">참조</span><span class="sxs-lookup"><span data-stu-id="5a466-140">See also</span></span>

- [<span data-ttu-id="5a466-141">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a466-141">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="5a466-142">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a466-142">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
