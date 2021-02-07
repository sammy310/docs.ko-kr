---
description: '자세히 알아보기: IMetaDataEmit:: TranslateSigWithScope 메서드'
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
ms.openlocfilehash: e5f4e522e993f2f391ca0c29e5fcc2cbb71775e8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99720934"
---
# <a name="imetadataemittranslatesigwithscope-method"></a><span data-ttu-id="4b275-103">IMetaDataEmit::TranslateSigWithScope 메서드</span><span class="sxs-lookup"><span data-stu-id="4b275-103">IMetaDataEmit::TranslateSigWithScope Method</span></span>

<span data-ttu-id="4b275-104">어셈블리를 현재 범위로 가져오고 병합 된 범위에 대 한 새 메타 데이터 서명을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4b275-104">Imports an assembly into the current scope and gets a new metadata signature for the merged scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b275-105">구문</span><span class="sxs-lookup"><span data-stu-id="4b275-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="4b275-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4b275-106">Parameters</span></span>  

 `pAssemImport`  
 <span data-ttu-id="4b275-107">진행 시그니처가 정의 된 가져오기 어셈블리에 대 한 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="4b275-107">[in] The interface for import assembly (where the signature is defined).</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="4b275-108">진행 어셈블리에 대 한 해시 blob입니다.</span><span class="sxs-lookup"><span data-stu-id="4b275-108">[in] The hash blob for the assembly.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="4b275-109">진행 의 바이트 수 `pbHashValue` 입니다.</span><span class="sxs-lookup"><span data-stu-id="4b275-109">[in] The count of bytes in `pbHashValue`.</span></span>  
  
 `import`  
 <span data-ttu-id="4b275-110">진행 메타 데이터 가져오기 범위에 대 한 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="4b275-110">[in] The interface for import metadata scope.</span></span>  
  
 `pbSigBlob`  
 <span data-ttu-id="4b275-111">진행 가져올 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="4b275-111">[in] The signature to be imported.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="4b275-112">진행 의 크기 (바이트)입니다 `pbSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="4b275-112">[in] The size, in bytes, of `pbSigBlob`.</span></span>  
  
 `pAssemEmit`  
 <span data-ttu-id="4b275-113">진행 내보내기 어셈블리에 대 한 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="4b275-113">[in] The interface for export assembly.</span></span>  
  
 `emit`  
 <span data-ttu-id="4b275-114">진행 내보내기 메타 데이터 범위에 대 한 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="4b275-114">[in] The interface for export metadata scope.</span></span>  
  
 `pvTranslatedSig`  
 <span data-ttu-id="4b275-115">제한이 번역 된 서명 blob을 저장할 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="4b275-115">[out] The buffer to hold the translated signature blob.</span></span>  
  
 `cbTranslatedSigMax`  
 <span data-ttu-id="4b275-116">진행 의 용량 (바이트)입니다 `pvTranslatedSig` .</span><span class="sxs-lookup"><span data-stu-id="4b275-116">[in] The capacity, in bytes, of `pvTranslatedSig`.</span></span>  
  
 `pcbTranslatedSig`  
 <span data-ttu-id="4b275-117">제한이 번역 된 시그니처의 실제 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="4b275-117">[out] The number of actual bytes in the translated signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b275-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4b275-118">Requirements</span></span>  

 <span data-ttu-id="4b275-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4b275-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b275-120">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="4b275-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4b275-121">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b275-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4b275-122">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b275-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b275-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b275-123">See also</span></span>

- [<span data-ttu-id="4b275-124">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4b275-124">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="4b275-125">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4b275-125">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="4b275-126">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4b275-126">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="4b275-127">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4b275-127">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="4b275-128">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4b275-128">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
