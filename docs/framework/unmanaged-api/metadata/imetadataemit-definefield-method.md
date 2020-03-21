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
ms.openlocfilehash: 8ca5ab70f60de4d783800fb18612a8f04cb9cee1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177710"
---
# <a name="imetadataemitdefinefield-method"></a><span data-ttu-id="2dbaa-102">IMetaDataEmit::DefineField 메서드</span><span class="sxs-lookup"><span data-stu-id="2dbaa-102">IMetaDataEmit::DefineField Method</span></span>
<span data-ttu-id="2dbaa-103">지정된 메타데이터 시그니처가 있는 필드에 대한 정의를 만들고 해당 필드 정의에 대한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2dbaa-103">Creates a definition for a field with the specified metadata signature, and gets a token to that field definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dbaa-104">구문</span><span class="sxs-lookup"><span data-stu-id="2dbaa-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="2dbaa-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2dbaa-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="2dbaa-106">【인】 둘러싸는 클래스 또는 인터페이스에 대한 `mdTypeDef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="2dbaa-106">[in] The `mdTypeDef` token for the enclosing class or interface.</span></span>  
  
 `szName`  
 <span data-ttu-id="2dbaa-107">【인】 유니코드의 필드 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2dbaa-107">[in] The field name in Unicode.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="2dbaa-108">【인】 필드 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2dbaa-108">[in] The field attributes.</span></span> <span data-ttu-id="2dbaa-109">이것은 값의 `CorFieldAttr` 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="2dbaa-109">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="2dbaa-110">【인】 필드 시그니처를 BLOB로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dbaa-110">[in] The field signature as a BLOB.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="2dbaa-111">【인】 의 바이트 `pvSigBlob`수입니다.</span><span class="sxs-lookup"><span data-stu-id="2dbaa-111">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="2dbaa-112">【인】 `ELEMENT_TYPE_` 에 대 한 상수 값입니다. *\**</span><span class="sxs-lookup"><span data-stu-id="2dbaa-112">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="2dbaa-113">이것은 값입니다. `CorElementType`</span><span class="sxs-lookup"><span data-stu-id="2dbaa-113">This is a `CorElementType` value.</span></span> <span data-ttu-id="2dbaa-114">필드에 대한 상수 값을 정의하지 `ELEMENT_TYPE_END`않으면 을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2dbaa-114">If not defining a constant value for the field, use `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="2dbaa-115">【인】 필드의 상수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2dbaa-115">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="2dbaa-116">【인】 의 (유니코드) 문자의 `pValue`크기입니다.</span><span class="sxs-lookup"><span data-stu-id="2dbaa-116">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
 `pmd`  
 <span data-ttu-id="2dbaa-117">【아웃】 할당된 토큰입니다. `mdFieldDef`</span><span class="sxs-lookup"><span data-stu-id="2dbaa-117">[out] The `mdFieldDef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2dbaa-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2dbaa-118">Requirements</span></span>  
 <span data-ttu-id="2dbaa-119">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2dbaa-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2dbaa-120">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="2dbaa-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2dbaa-121">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="2dbaa-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2dbaa-122">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2dbaa-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dbaa-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2dbaa-123">See also</span></span>

- [<span data-ttu-id="2dbaa-124">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2dbaa-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="2dbaa-125">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2dbaa-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
