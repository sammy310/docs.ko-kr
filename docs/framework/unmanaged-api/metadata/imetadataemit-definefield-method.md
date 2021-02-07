---
description: IMetaDataEmit::D efineField 메서드에 대해 자세히 알아보세요.
title: IMetaDataEmit::DefineField 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineField
helpviewer_keywords:
- IMetaDataEmit::DefineField method [.NET Framework metadata]
- DefineField method, IMetaDataEmit interface [.NET Framework metadata
ms.assetid: 6b5be4fc-2e86-499c-8b09-833160bca767
topic_type:
- apiref
ms.openlocfilehash: 7636b1521de721cc183305e8a0763ff0a61f331b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753447"
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="76937-103">IMetaDataEmit::DefineField 메서드</span><span class="sxs-lookup"><span data-stu-id="76937-103">IMetaDataEmit::DefineField Method</span></span>

<span data-ttu-id="76937-104">지정 된 메타 데이터 시그니처를 사용 하 여 필드에 대 한 정의를 만들고 해당 필드 정의에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="76937-104">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76937-105">구문</span><span class="sxs-lookup"><span data-stu-id="76937-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineField (
    [in]  mdTypeDef   td,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwFieldFlags,
    [in]  PCCOR_SIGNATURE pvSigBlob,
    [in]  ULONG       cbSigBlob,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue,
    [out] mdFieldDef  *pmd
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76937-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="76937-106">Parameters</span></span>  

 `td`  
 <span data-ttu-id="76937-107">진행 `mdTypeDef` 바깥쪽 클래스 또는 인터페이스에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="76937-107">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="76937-108">진행 유니코드의 필드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="76937-108">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="76937-109">진행 필드 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="76937-109">[in] The field attributes.</span></span> <span data-ttu-id="76937-110">값의 비트 마스크입니다 `CorFieldAttr` .</span><span class="sxs-lookup"><span data-stu-id="76937-110">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="76937-111">진행 BLOB으로 필드 시그니처입니다.</span><span class="sxs-lookup"><span data-stu-id="76937-111">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="76937-112">진행 의 바이트 수 `pvSigBlob` 입니다.</span><span class="sxs-lookup"><span data-stu-id="76937-112">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="76937-113">진행 `ELEMENT_TYPE_` *\** 상수 값에 대 한입니다.</span><span class="sxs-lookup"><span data-stu-id="76937-113">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="76937-114">`CorElementType`값입니다.</span><span class="sxs-lookup"><span data-stu-id="76937-114">This is a `CorElementType` value.</span></span> <span data-ttu-id="76937-115">필드에 대 한 상수 값을 정의 하지 않는 경우를 사용 `ELEMENT_TYPE_END` 합니다.</span><span class="sxs-lookup"><span data-stu-id="76937-115">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="76937-116">진행 필드의 상수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="76937-116">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="76937-117">진행 의 (유니코드) 문자 크기입니다 `pValue` .</span><span class="sxs-lookup"><span data-stu-id="76937-117">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="76937-118">제한이 `mdFieldDef` 할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="76937-118">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76937-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="76937-119">Requirements</span></span>  

 <span data-ttu-id="76937-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76937-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76937-121">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="76937-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="76937-122">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76937-122">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="76937-123">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76937-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76937-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="76937-124">See also</span></span>

- [<span data-ttu-id="76937-125">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="76937-125">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="76937-126">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="76937-126">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
