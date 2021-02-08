---
description: '자세히 알아보기: IMetaDataImport:: EnumUnresolvedMethods 메서드'
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
ms.openlocfilehash: e894ecdde91a2263783234d73fa50d890a13e413
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799332"
---
# <a name="imetadataimportenumunresolvedmethods-method"></a><span data-ttu-id="c1162-103">IMetaDataImport::EnumUnresolvedMethods 메서드</span><span class="sxs-lookup"><span data-stu-id="c1162-103">IMetaDataImport::EnumUnresolvedMethods Method</span></span>

<span data-ttu-id="c1162-104">현재 메타데이터 범위에서 확인되지 않은 메서드를 나타내는 MemberDef 토큰을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="c1162-104">Enumerates MemberDef tokens representing the unresolved methods in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1162-105">구문</span><span class="sxs-lookup"><span data-stu-id="c1162-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumUnresolvedMethods (  
   [in, out] HCORENUM    *phEnum,  
   [out]     mdToken     rMethods[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1162-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c1162-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="c1162-107">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c1162-107">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="c1162-108">이 메서드의 첫 번째 호출에서는 NULL 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1162-108">This must be NULL for the first call of this method.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="c1162-109">제한이 MemberDef 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="c1162-109">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c1162-110">[in] `rMethods` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="c1162-110">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="c1162-111">제한이 에서 반환 되는 MemberDef 토큰 수입니다 `rMethods` .</span><span class="sxs-lookup"><span data-stu-id="c1162-111">[out] The number of MemberDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c1162-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="c1162-112">Return Value</span></span>  
  
|<span data-ttu-id="c1162-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c1162-113">HRESULT</span></span>|<span data-ttu-id="c1162-114">설명</span><span class="sxs-lookup"><span data-stu-id="c1162-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c1162-115">`EnumUnresolvedMethods` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c1162-115">`EnumUnresolvedMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c1162-116">열거할 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1162-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="c1162-117">이 경우는 `pcTokens` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="c1162-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1162-118">설명</span><span class="sxs-lookup"><span data-stu-id="c1162-118">Remarks</span></span>  

 <span data-ttu-id="c1162-119">확인 되지 않은 메서드는 선언 되었지만 구현 되지 않은 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="c1162-119">An unresolved method is one that has been declared but not implemented.</span></span> <span data-ttu-id="c1162-120">메서드가로 표시 되 `miForwardRef` 고 `mdPinvokeImpl` 또는 `miRuntime` 가 0으로 설정 된 경우 메서드는 열거형에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1162-120">A method is included in the enumeration if the method is marked `miForwardRef` and either `mdPinvokeImpl` or `miRuntime` is set to zero.</span></span> <span data-ttu-id="c1162-121">즉, 확인 되지 않은 메서드는로 표시 `miForwardRef` 되었지만 관리 되지 않는 코드 (PInvoke를 통해 도달)에 구현 되지 않거나 런타임 자체에서 내부적으로 구현 되지 않는 클래스 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="c1162-121">In other words, an unresolved method is a class method that is marked `miForwardRef` but which is not implemented in unmanaged code (reached via PInvoke) nor implemented internally by the runtime itself</span></span>  
  
 <span data-ttu-id="c1162-122">열거형은 모듈 범위 (globals) 또는 인터페이스 또는 추상 클래스에 정의 된 모든 메서드를 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1162-122">The enumeration excludes all methods that are defined either at module scope (globals) or in interfaces or abstract classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1162-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c1162-123">Requirements</span></span>  

 <span data-ttu-id="c1162-124">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1162-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1162-125">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="c1162-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c1162-126">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1162-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c1162-127">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1162-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1162-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c1162-128">See also</span></span>

- [<span data-ttu-id="c1162-129">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c1162-129">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="c1162-130">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c1162-130">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
