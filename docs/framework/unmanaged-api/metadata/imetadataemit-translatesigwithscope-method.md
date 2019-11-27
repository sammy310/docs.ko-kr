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
# <a name="imetadataemittranslatesigwithscope-method"></a><span data-ttu-id="502a1-102">IMetaDataEmit::TranslateSigWithScope 메서드</span><span class="sxs-lookup"><span data-stu-id="502a1-102">IMetaDataEmit::TranslateSigWithScope Method</span></span>
<span data-ttu-id="502a1-103">어셈블리를 현재 범위로 가져오고 병합 된 범위에 대 한 새 메타 데이터 서명을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="502a1-103">Imports an assembly into the current scope and gets a new metadata signature for the merged scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="502a1-104">구문</span><span class="sxs-lookup"><span data-stu-id="502a1-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="502a1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="502a1-105">Parameters</span></span>  
 `pAssemImport`  
 <span data-ttu-id="502a1-106">[in] \(서명을 정의 됨) 가져오기 어셈블리에 대 한 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="502a1-106">[in] The interface for import assembly (where the signature is defined).</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="502a1-107">진행 어셈블리에 대 한 해시 blob입니다.</span><span class="sxs-lookup"><span data-stu-id="502a1-107">[in] The hash blob for the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="502a1-108">진행 `pbHashValue`바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="502a1-108">[in] The count of bytes in `pbHashValue`.</span></span>  
  
 `import`  
 <span data-ttu-id="502a1-109">진행 메타 데이터 가져오기 범위에 대 한 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="502a1-109">[in] The interface for import metadata scope.</span></span>  
  
 `pbSigBlob`  
 <span data-ttu-id="502a1-110">진행 가져올 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="502a1-110">[in] The signature to be imported.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="502a1-111">진행 `pbSigBlob`의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="502a1-111">[in] The size, in bytes, of `pbSigBlob`.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="502a1-112">진행 내보내기 어셈블리에 대 한 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="502a1-112">[in] The interface for export assembly.</span></span>  
  
 `emit`  
 <span data-ttu-id="502a1-113">진행 내보내기 메타 데이터 범위에 대 한 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="502a1-113">[in] The interface for export metadata scope.</span></span>  
  
 `pvTranslatedSig`  
 <span data-ttu-id="502a1-114">제한이 번역 된 서명 blob을 저장할 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="502a1-114">[out] The buffer to hold the translated signature blob.</span></span>  
  
 `cbTranslatedSigMax`  
 <span data-ttu-id="502a1-115">진행 `pvTranslatedSig`의 용량 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="502a1-115">[in] The capacity, in bytes, of `pvTranslatedSig`.</span></span>  
  
 `pcbTranslatedSig`  
 <span data-ttu-id="502a1-116">제한이 번역 된 시그니처의 실제 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="502a1-116">[out] The number of actual bytes in the translated signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="502a1-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="502a1-117">Requirements</span></span>  
 <span data-ttu-id="502a1-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="502a1-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="502a1-119">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="502a1-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="502a1-120">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="502a1-120">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="502a1-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="502a1-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="502a1-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="502a1-122">See also</span></span>

- [<span data-ttu-id="502a1-123">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="502a1-123">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="502a1-124">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="502a1-124">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="502a1-125">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="502a1-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="502a1-126">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="502a1-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="502a1-127">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="502a1-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
