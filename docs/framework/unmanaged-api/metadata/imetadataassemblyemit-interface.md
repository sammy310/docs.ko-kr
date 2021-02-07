---
description: '자세히 알아보기: IMetaDataAssemblyEmit 인터페이스'
title: IMetaDataAssemblyEmit 인터페이스
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit
helpviewer_keywords:
- IMetaDataAssemblyEmit interface [.NET Framework metadata]
ms.assetid: 34fb03cc-2285-4a45-ac48-ad993b7a921a
topic_type:
- apiref
ms.openlocfilehash: bcfca4eedc14f2292c40874d86c4984b4c1948f5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678213"
---
# <a name="imetadataassemblyemit-interface"></a><span data-ttu-id="b2f6c-103">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b2f6c-103">IMetaDataAssemblyEmit Interface</span></span>

<span data-ttu-id="b2f6c-104">공용 언어 런타임에서 리소스를 확인하고 소비하는 데 사용되는 자체 설명 모델을 지원하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b2f6c-104">Provides methods that support the self-description model used by the common language runtime to resolve and consume resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b2f6c-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b2f6c-105">Methods</span></span>  
  
|<span data-ttu-id="b2f6c-106">메서드</span><span class="sxs-lookup"><span data-stu-id="b2f6c-106">Method</span></span>|<span data-ttu-id="b2f6c-107">설명</span><span class="sxs-lookup"><span data-stu-id="b2f6c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b2f6c-108">DefineAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="b2f6c-108">DefineAssembly Method</span></span>](imetadataassemblyemit-defineassembly-method.md)|<span data-ttu-id="b2f6c-109">지정된 어셈블리에 대한 메타데이터를 포함하는 어셈블리 데이터 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b2f6c-109">Creates an assembly data structure containing metadata for the specified assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="b2f6c-110">DefineAssemblyRef 메서드</span><span class="sxs-lookup"><span data-stu-id="b2f6c-110">DefineAssemblyRef Method</span></span>](imetadataassemblyemit-defineassemblyref-method.md)|<span data-ttu-id="b2f6c-111">이 어셈블리가 참조하는 어셈블리에 대한 메타데이터를 포함하는 `AssemblyRef` 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b2f6c-111">Creates an `AssemblyRef` structure containing metadata for the assembly that this assembly references, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="b2f6c-112">DefineExportedType 메서드</span><span class="sxs-lookup"><span data-stu-id="b2f6c-112">DefineExportedType Method</span></span>](imetadataassemblyemit-defineexportedtype-method.md)|<span data-ttu-id="b2f6c-113">지정된 내보낸 형식에 대한 메타데이터를 포함하는 `ExportedType` 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b2f6c-113">Creates an `ExportedType` structure containing metadata for the specified exported type, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="b2f6c-114">DefineFile 메서드</span><span class="sxs-lookup"><span data-stu-id="b2f6c-114">DefineFile Method</span></span>](imetadataassemblyemit-definefile-method.md)|<span data-ttu-id="b2f6c-115">이 어셈블리가 참조하는 어셈블리에 대한 메타데이터를 포함하는 `File` 메타데이터 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b2f6c-115">Creates a `File` metadata structure containing metadata for assembly referenced by this assembly, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="b2f6c-116">DefineManifestResource 메서드</span><span class="sxs-lookup"><span data-stu-id="b2f6c-116">DefineManifestResource Method</span></span>](imetadataassemblyemit-definemanifestresource-method.md)|<span data-ttu-id="b2f6c-117">지정된 매니페스트 리소스에 대한 메타데이터를 포함하는 `ManifestResource` 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b2f6c-117">Creates a `ManifestResource` structure containing metadata for the specified manifest resource, and returns the associated metadata token.</span></span>|  
|[<span data-ttu-id="b2f6c-118">SetAssemblyProps 메서드</span><span class="sxs-lookup"><span data-stu-id="b2f6c-118">SetAssemblyProps Method</span></span>](imetadataassemblyemit-setassemblyprops-method.md)|<span data-ttu-id="b2f6c-119">지정된 `Assembly` 메타데이터 구조를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="b2f6c-119">Modifies the specified `Assembly` metadata structure.</span></span>|  
|[<span data-ttu-id="b2f6c-120">SetAssemblyRefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="b2f6c-120">SetAssemblyRefProps Method</span></span>](imetadataassemblyemit-setassemblyrefprops-method.md)|<span data-ttu-id="b2f6c-121">지정된 `AssemblyRef` 메타데이터 구조를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="b2f6c-121">Modifies the specified `AssemblyRef` metadata structure.</span></span>|  
|[<span data-ttu-id="b2f6c-122">SetExportedTypeProps 메서드</span><span class="sxs-lookup"><span data-stu-id="b2f6c-122">SetExportedTypeProps Method</span></span>](imetadataassemblyemit-setexportedtypeprops-method.md)|<span data-ttu-id="b2f6c-123">지정된 `ExportedType` 메타데이터 구조를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="b2f6c-123">Modifies the specified `ExportedType` metadata structure.</span></span>|  
|[<span data-ttu-id="b2f6c-124">SetFileProps 메서드</span><span class="sxs-lookup"><span data-stu-id="b2f6c-124">SetFileProps Method</span></span>](imetadataassemblyemit-setfileprops-method.md)|<span data-ttu-id="b2f6c-125">지정된 `File` 메타데이터 구조를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="b2f6c-125">Modifies the specified `File` metadata structure.</span></span>|  
|[<span data-ttu-id="b2f6c-126">SetManifestResourceProps 메서드</span><span class="sxs-lookup"><span data-stu-id="b2f6c-126">SetManifestResourceProps Method</span></span>](imetadataassemblyemit-setmanifestresourceprops-method.md)|<span data-ttu-id="b2f6c-127">지정된 `ManifestResource` 메타데이터 구조를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="b2f6c-127">Modifies the specified `ManifestResource` metadata structure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2f6c-128">설명</span><span class="sxs-lookup"><span data-stu-id="b2f6c-128">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2f6c-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b2f6c-129">Requirements</span></span>  

 <span data-ttu-id="b2f6c-130">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b2f6c-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2f6c-131">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="b2f6c-131">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b2f6c-132">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2f6c-132">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b2f6c-133">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2f6c-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2f6c-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2f6c-134">See also</span></span>

- [<span data-ttu-id="b2f6c-135">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b2f6c-135">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="b2f6c-136">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b2f6c-136">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
