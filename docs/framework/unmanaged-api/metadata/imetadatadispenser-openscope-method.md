---
title: IMetaDataDispenser::OpenScope 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScope
helpviewer_keywords:
- IMetaDataDispenser::OpenScope method [.NET Framework metadata]
- OpenScope method, IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 65063ad5-e0d9-4c01-8f8b-9a5950109fa6
topic_type:
- apiref
ms.openlocfilehash: 5ce1af82631531f8f7105fbf92ba78db3cca437b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442321"
---
# <a name="imetadatadispenseropenscope-method"></a><span data-ttu-id="8743a-102">IMetaDataDispenser::OpenScope 메서드</span><span class="sxs-lookup"><span data-stu-id="8743a-102">IMetaDataDispenser::OpenScope Method</span></span>
<span data-ttu-id="8743a-103">Opens an existing, on-disk file and maps its metadata into memory.</span><span class="sxs-lookup"><span data-stu-id="8743a-103">Opens an existing, on-disk file and maps its metadata into memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8743a-104">구문</span><span class="sxs-lookup"><span data-stu-id="8743a-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope (  
    [in]  LPCWSTR     szScope,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8743a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8743a-105">Parameters</span></span>  
 `szScope`  
 <span data-ttu-id="8743a-106">[in] The name of the file to be opened.</span><span class="sxs-lookup"><span data-stu-id="8743a-106">[in] The name of the file to be opened.</span></span> <span data-ttu-id="8743a-107">The file must contain common language runtime (CLR) metadata.</span><span class="sxs-lookup"><span data-stu-id="8743a-107">The file must contain common language runtime (CLR) metadata.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="8743a-108">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span><span class="sxs-lookup"><span data-stu-id="8743a-108">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="8743a-109">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span><span class="sxs-lookup"><span data-stu-id="8743a-109">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="8743a-110">The value of `riid` must specify one of the "import" or "emit" interfaces.</span><span class="sxs-lookup"><span data-stu-id="8743a-110">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="8743a-111">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span><span class="sxs-lookup"><span data-stu-id="8743a-111">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="8743a-112">[out] The pointer to the returned interface.</span><span class="sxs-lookup"><span data-stu-id="8743a-112">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8743a-113">주의</span><span class="sxs-lookup"><span data-stu-id="8743a-113">Remarks</span></span>  
 <span data-ttu-id="8743a-114">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span><span class="sxs-lookup"><span data-stu-id="8743a-114">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="8743a-115">If the target file does not contain CLR metadata, the `OpenScope` method will fail.</span><span class="sxs-lookup"><span data-stu-id="8743a-115">If the target file does not contain CLR metadata, the `OpenScope` method will fail.</span></span>  
  
 <span data-ttu-id="8743a-116">In the .NET Framework version 1.0 and version 1.1, if a scope is opened with `dwOpenFlags` set to ofRead, it is eligible for sharing.</span><span class="sxs-lookup"><span data-stu-id="8743a-116">In the .NET Framework version 1.0 and version 1.1, if a scope is opened with `dwOpenFlags` set to ofRead, it is eligible for sharing.</span></span> <span data-ttu-id="8743a-117">That is, if subsequent calls to `OpenScope` pass in the name of a file that was previously opened, the existing scope is reused and a new set of data structures is not created.</span><span class="sxs-lookup"><span data-stu-id="8743a-117">That is, if subsequent calls to `OpenScope` pass in the name of a file that was previously opened, the existing scope is reused and a new set of data structures is not created.</span></span> <span data-ttu-id="8743a-118">However, problems can arise due to this sharing.</span><span class="sxs-lookup"><span data-stu-id="8743a-118">However, problems can arise due to this sharing.</span></span>  
  
 <span data-ttu-id="8743a-119">In the .NET Framework version 2.0, scopes opened with `dwOpenFlags` set to ofRead are no longer shared.</span><span class="sxs-lookup"><span data-stu-id="8743a-119">In the .NET Framework version 2.0, scopes opened with `dwOpenFlags` set to ofRead are no longer shared.</span></span> <span data-ttu-id="8743a-120">Use the ofReadOnly value to allow the scope to be shared.</span><span class="sxs-lookup"><span data-stu-id="8743a-120">Use the ofReadOnly value to allow the scope to be shared.</span></span> <span data-ttu-id="8743a-121">When a scope is shared, queries that use "read/write" metadata interfaces will fail.</span><span class="sxs-lookup"><span data-stu-id="8743a-121">When a scope is shared, queries that use "read/write" metadata interfaces will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8743a-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8743a-122">Requirements</span></span>  
 <span data-ttu-id="8743a-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8743a-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8743a-124">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8743a-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8743a-125">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8743a-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8743a-126">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8743a-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8743a-127">참조</span><span class="sxs-lookup"><span data-stu-id="8743a-127">See also</span></span>

- [<span data-ttu-id="8743a-128">IMetaDataDispenser 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8743a-128">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="8743a-129">IMetaDataDispenserEx 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8743a-129">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="8743a-130">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8743a-130">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="8743a-131">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8743a-131">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="8743a-132">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8743a-132">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="8743a-133">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8743a-133">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="8743a-134">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8743a-134">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="8743a-135">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8743a-135">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
