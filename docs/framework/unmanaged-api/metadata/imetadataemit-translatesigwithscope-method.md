---
title: IMetaDataEmit::TranslateSigWithScope 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.TranslateSigWithScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::TranslateSigWithScope
helpviewer_keywords:
- TranslateSigWithScope method [.NET Framework metadata]
- IMetaDataEmit::TranslateSigWithScope method [.NET Framework metadata]
ms.assetid: 47915d33-b7bf-409e-b484-4ee1df15de22
topic_type:
- apiref
ms.openlocfilehash: cea84f47a5289df4bc9c50381e18d7077b3b8dad
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440483"
---
# <a name="imetadataemittranslatesigwithscope-method"></a><span data-ttu-id="b4ac0-102">IMetaDataEmit::TranslateSigWithScope 메서드</span><span class="sxs-lookup"><span data-stu-id="b4ac0-102">IMetaDataEmit::TranslateSigWithScope Method</span></span>
<span data-ttu-id="b4ac0-103">Imports an assembly into the current scope and gets a new metadata signature for the merged scope.</span><span class="sxs-lookup"><span data-stu-id="b4ac0-103">Imports an assembly into the current scope and gets a new metadata signature for the merged scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4ac0-104">구문</span><span class="sxs-lookup"><span data-stu-id="b4ac0-104">Syntax</span></span>  
  
```cpp  
HRESULT TranslateSigWithScope (   
    [in]  IMetaDataAssemblyImport   *pAssemImport,   
    [in]  const void                *pbHashValue,   
    [in]  ULONG                     cbHashValue,   
    [in]  IMetaDataImport           *import,   
    [in]  PCCOR_SIGNATURE           pbSigBlob,   
    [in]  ULONG                     cbSigBlob,  
    [in]  IMetaDataAssemblyEmit     *pAssemEmit,   
    [in]  IMetaDataEmit             *emit,   
    [out] PCOR_SIGNATURE            pvTranslatedSig,   
    [in]  ULONG                     cbTranslatedSigMax,   
    [out] ULONG                     *pcbTranslatedSig   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4ac0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b4ac0-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="b4ac0-106">[in] The interface for import assembly (where the signature is defined).</span><span class="sxs-lookup"><span data-stu-id="b4ac0-106">[in] The interface for import assembly (where the signature is defined).</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="b4ac0-107">[in] The hash blob for the assembly.</span><span class="sxs-lookup"><span data-stu-id="b4ac0-107">[in] The hash blob for the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="b4ac0-108">[in] The count of bytes in `pbHashValue`.</span><span class="sxs-lookup"><span data-stu-id="b4ac0-108">[in] The count of bytes in `pbHashValue`.</span></span>  
  
 `import`  
 <span data-ttu-id="b4ac0-109">[in] The interface for import metadata scope.</span><span class="sxs-lookup"><span data-stu-id="b4ac0-109">[in] The interface for import metadata scope.</span></span>  
  
 `pbSigBlob`  
 <span data-ttu-id="b4ac0-110">[in] The signature to be imported.</span><span class="sxs-lookup"><span data-stu-id="b4ac0-110">[in] The signature to be imported.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="b4ac0-111">[in] The size, in bytes, of `pbSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="b4ac0-111">[in] The size, in bytes, of `pbSigBlob`.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="b4ac0-112">[in] The interface for export assembly.</span><span class="sxs-lookup"><span data-stu-id="b4ac0-112">[in] The interface for export assembly.</span></span>  
  
 `emit`  
 <span data-ttu-id="b4ac0-113">[in] The interface for export metadata scope.</span><span class="sxs-lookup"><span data-stu-id="b4ac0-113">[in] The interface for export metadata scope.</span></span>  
  
 `pvTranslatedSig`  
 <span data-ttu-id="b4ac0-114">[out] The buffer to hold the translated signature blob.</span><span class="sxs-lookup"><span data-stu-id="b4ac0-114">[out] The buffer to hold the translated signature blob.</span></span>  
  
 `cbTranslatedSigMax`  
 <span data-ttu-id="b4ac0-115">[in] The capacity, in bytes, of `pvTranslatedSig`.</span><span class="sxs-lookup"><span data-stu-id="b4ac0-115">[in] The capacity, in bytes, of `pvTranslatedSig`.</span></span>  
  
 `pcbTranslatedSig`  
 <span data-ttu-id="b4ac0-116">[out] The number of actual bytes in the translated signature.</span><span class="sxs-lookup"><span data-stu-id="b4ac0-116">[out] The number of actual bytes in the translated signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4ac0-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b4ac0-117">Requirements</span></span>  
 <span data-ttu-id="b4ac0-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b4ac0-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4ac0-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b4ac0-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b4ac0-120">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b4ac0-120">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b4ac0-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4ac0-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4ac0-122">참조</span><span class="sxs-lookup"><span data-stu-id="b4ac0-122">See also</span></span>

- [<span data-ttu-id="b4ac0-123">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b4ac0-123">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="b4ac0-124">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b4ac0-124">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="b4ac0-125">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b4ac0-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="b4ac0-126">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b4ac0-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="b4ac0-127">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b4ac0-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
