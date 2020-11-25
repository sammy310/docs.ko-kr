---
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
ms.openlocfilehash: 2bc2b983171dc41d5ac37eda0359f1aaee4ebd6e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725757"
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="8e9f0-102">IMetaDataEmit::DefineField 메서드</span><span class="sxs-lookup"><span data-stu-id="8e9f0-102">IMetaDataEmit::DefineField Method</span></span>

<span data-ttu-id="8e9f0-103">지정 된 메타 데이터 시그니처를 사용 하 여 필드에 대 한 정의를 만들고 해당 필드 정의에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8e9f0-103">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e9f0-104">구문</span><span class="sxs-lookup"><span data-stu-id="8e9f0-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="8e9f0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8e9f0-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="8e9f0-106">진행 `mdTypeDef` 바깥쪽 클래스 또는 인터페이스에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="8e9f0-106">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="8e9f0-107">진행 유니코드의 필드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8e9f0-107">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="8e9f0-108">진행 필드 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="8e9f0-108">[in] The field attributes.</span></span> <span data-ttu-id="8e9f0-109">값의 비트 마스크입니다 `CorFieldAttr` .</span><span class="sxs-lookup"><span data-stu-id="8e9f0-109">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="8e9f0-110">진행 BLOB으로 필드 시그니처입니다.</span><span class="sxs-lookup"><span data-stu-id="8e9f0-110">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="8e9f0-111">진행 의 바이트 수 `pvSigBlob` 입니다.</span><span class="sxs-lookup"><span data-stu-id="8e9f0-111">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="8e9f0-112">진행 `ELEMENT_TYPE_` *\** 상수 값에 대 한입니다.</span><span class="sxs-lookup"><span data-stu-id="8e9f0-112">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="8e9f0-113">`CorElementType`값입니다.</span><span class="sxs-lookup"><span data-stu-id="8e9f0-113">This is a `CorElementType` value.</span></span> <span data-ttu-id="8e9f0-114">필드에 대 한 상수 값을 정의 하지 않는 경우를 사용 `ELEMENT_TYPE_END` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e9f0-114">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="8e9f0-115">진행 필드의 상수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8e9f0-115">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="8e9f0-116">진행 의 (유니코드) 문자 크기입니다 `pValue` .</span><span class="sxs-lookup"><span data-stu-id="8e9f0-116">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="8e9f0-117">제한이 `mdFieldDef` 할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="8e9f0-117">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e9f0-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8e9f0-118">Requirements</span></span>  

 <span data-ttu-id="8e9f0-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8e9f0-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e9f0-120">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="8e9f0-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8e9f0-121">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8e9f0-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8e9f0-122">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e9f0-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e9f0-123">참조</span><span class="sxs-lookup"><span data-stu-id="8e9f0-123">See also</span></span>

- [<span data-ttu-id="8e9f0-124">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8e9f0-124">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="8e9f0-125">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8e9f0-125">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
