---
title: IMetaDataImport::GetMethodSemantics 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodSemantics
helpviewer_keywords:
- GetMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::GetMethodSemantics method [.NET Framework metadata]
ms.assetid: 5e018eaa-d60e-4a0b-a2c5-8c36bd09d905
topic_type:
- apiref
ms.openlocfilehash: cc01a417c3246ad2554c506f21e37a3cbbdeb991
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733190"
---
# <a name="imetadataimportgetmethodsemantics-method"></a><span data-ttu-id="87e3c-102">IMetaDataImport::GetMethodSemantics 메서드</span><span class="sxs-lookup"><span data-stu-id="87e3c-102">IMetaDataImport::GetMethodSemantics Method</span></span>

<span data-ttu-id="87e3c-103">지정 된 MethodDef 토큰이 참조 하는 메서드와 지정 된 EventProp 토큰이 참조 하는 쌍을 이루는 속성 및 이벤트 간의 관계를 나타내는 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="87e3c-103">Gets flags indicating the relationship between the method referenced by the specified MethodDef token and the paired property and event referenced by the specified EventProp token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87e3c-104">구문</span><span class="sxs-lookup"><span data-stu-id="87e3c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodSemantics (  
   [in]  mdMethodDef   mb,  
   [in]  mdToken       tkEventProp,  
   [out] DWORD         *pdwSemanticsFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87e3c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="87e3c-105">Parameters</span></span>  

 `mb`  
 <span data-ttu-id="87e3c-106">진행 의미 체계 역할 정보를 가져올 메서드를 나타내는 MethodDef 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="87e3c-106">[in] A MethodDef token representing the method to get the semantic role information for.</span></span>  
  
 `tkEventProp`  
 <span data-ttu-id="87e3c-107">진행 메서드 역할을 가져올 쌍을 이루는 속성 및 이벤트를 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="87e3c-107">[in] A token representing the paired property and event for which to get the method's role.</span></span>  
  
 `pdwSemanticsFlags`  
 <span data-ttu-id="87e3c-108">제한이 연결 된 의미 체계 플래그에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="87e3c-108">[out] A pointer to the associated semantics flags.</span></span> <span data-ttu-id="87e3c-109">이 값은 [CorMethodSemanticsAttr](cormethodsemanticsattr-enumeration.md) 열거형의 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="87e3c-109">This value is a bitmask from the [CorMethodSemanticsAttr](cormethodsemanticsattr-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87e3c-110">설명</span><span class="sxs-lookup"><span data-stu-id="87e3c-110">Remarks</span></span>  

 <span data-ttu-id="87e3c-111">[IMetaDataEmit::D efineProperty](imetadataemit-defineproperty-method.md) 메서드는 메서드의 의미 체계 플래그를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="87e3c-111">The [IMetaDataEmit::DefineProperty](imetadataemit-defineproperty-method.md) method sets a method's semantics flags.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87e3c-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="87e3c-112">Requirements</span></span>  

 <span data-ttu-id="87e3c-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87e3c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87e3c-114">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="87e3c-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="87e3c-115">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87e3c-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="87e3c-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87e3c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87e3c-117">참조</span><span class="sxs-lookup"><span data-stu-id="87e3c-117">See also</span></span>

- [<span data-ttu-id="87e3c-118">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87e3c-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="87e3c-119">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87e3c-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
