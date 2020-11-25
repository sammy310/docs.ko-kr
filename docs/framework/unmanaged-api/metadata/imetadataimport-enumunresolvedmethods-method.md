---
title: IMetaDataImport::EnumUnresolvedMethods 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUnresolvedMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUnresolvedMethods
helpviewer_keywords:
- EnumUnresolvedMethods method [.NET Framework metadata]
- IMetaDataImport::EnumUnresolvedMethods method [.NET Framework metadata]
ms.assetid: eb3187d7-74cf-44b1-aeeb-7a8d2b60e3b7
topic_type:
- apiref
ms.openlocfilehash: 6b5e7bbe2303a200d7829fea12e228a513595f97
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716554"
---
# <a name="imetadataimportenumunresolvedmethods-method"></a><span data-ttu-id="398ee-102">IMetaDataImport::EnumUnresolvedMethods 메서드</span><span class="sxs-lookup"><span data-stu-id="398ee-102">IMetaDataImport::EnumUnresolvedMethods Method</span></span>

<span data-ttu-id="398ee-103">현재 메타데이터 범위에서 확인되지 않은 메서드를 나타내는 MemberDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="398ee-103">Enumerates MemberDef tokens representing the unresolved methods in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="398ee-104">구문</span><span class="sxs-lookup"><span data-stu-id="398ee-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumUnresolvedMethods (  
   [in, out] HCORENUM    *phEnum,  
   [out]     mdToken     rMethods[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="398ee-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="398ee-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="398ee-106">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="398ee-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="398ee-107">이 메서드의 첫 번째 호출에서는 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="398ee-107">This must be NULL for the first call of this method.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="398ee-108">제한이 MemberDef 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="398ee-108">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="398ee-109">[in] `rMethods` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="398ee-109">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="398ee-110">제한이 에서 반환 되는 MemberDef 토큰 수입니다 `rMethods` .</span><span class="sxs-lookup"><span data-stu-id="398ee-110">[out] The number of MemberDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="398ee-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="398ee-111">Return Value</span></span>  
  
|<span data-ttu-id="398ee-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="398ee-112">HRESULT</span></span>|<span data-ttu-id="398ee-113">설명</span><span class="sxs-lookup"><span data-stu-id="398ee-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="398ee-114">`EnumUnresolvedMethods` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="398ee-114">`EnumUnresolvedMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="398ee-115">열거할 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="398ee-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="398ee-116">이 경우는 `pcTokens` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="398ee-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="398ee-117">설명</span><span class="sxs-lookup"><span data-stu-id="398ee-117">Remarks</span></span>  

 <span data-ttu-id="398ee-118">확인 되지 않은 메서드는 선언 되었지만 구현 되지 않은 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="398ee-118">An unresolved method is one that has been declared but not implemented.</span></span> <span data-ttu-id="398ee-119">메서드가로 표시 되 `miForwardRef` 고 `mdPinvokeImpl` 또는 `miRuntime` 가 0으로 설정 된 경우 메서드는 열거형에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="398ee-119">A method is included in the enumeration if the method is marked `miForwardRef` and either `mdPinvokeImpl` or `miRuntime` is set to zero.</span></span> <span data-ttu-id="398ee-120">즉, 확인 되지 않은 메서드는로 표시 `miForwardRef` 되었지만 관리 되지 않는 코드 (PInvoke를 통해 도달)에 구현 되지 않거나 런타임 자체에서 내부적으로 구현 되지 않는 클래스 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="398ee-120">In other words, an unresolved method is a class method that is marked `miForwardRef` but which is not implemented in unmanaged code (reached via PInvoke) nor implemented internally by the runtime itself</span></span>  
  
 <span data-ttu-id="398ee-121">열거형은 모듈 범위 (globals) 또는 인터페이스 또는 추상 클래스에 정의 된 모든 메서드를 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="398ee-121">The enumeration excludes all methods that are defined either at module scope (globals) or in interfaces or abstract classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="398ee-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="398ee-122">Requirements</span></span>  

 <span data-ttu-id="398ee-123">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="398ee-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="398ee-124">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="398ee-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="398ee-125">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="398ee-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="398ee-126">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="398ee-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="398ee-127">참조</span><span class="sxs-lookup"><span data-stu-id="398ee-127">See also</span></span>

- [<span data-ttu-id="398ee-128">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="398ee-128">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="398ee-129">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="398ee-129">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
