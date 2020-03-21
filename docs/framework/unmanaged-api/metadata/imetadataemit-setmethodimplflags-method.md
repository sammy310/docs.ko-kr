---
title: IMetaDataEmit::SetMethodImplFlags 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodImplFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodImplFlags
helpviewer_keywords:
- IMetaDataEmit::SetMethodImplFlags method [.NET Framework metadata]
- SetMethodImpFlags method [.NET Framework metadata]
ms.assetid: 4bc82d9b-9544-4be3-ba51-a2d4d806158a
topic_type:
- apiref
ms.openlocfilehash: 7ed7770f26ea4620d79f3be3f67e72f73c75057d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175631"
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="2bc7a-102">IMetaDataEmit::SetMethodImplFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="2bc7a-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>
<span data-ttu-id="2bc7a-103">지정된 토큰에서 참조하는 상속된 메서드 구현의 메타데이터 서명을 설정하거나 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="2bc7a-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bc7a-104">구문</span><span class="sxs-lookup"><span data-stu-id="2bc7a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodImplFlags (
    [in]  mdMethodDef   md,
    [in]  DWORD         dwImplFlags
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bc7a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2bc7a-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="2bc7a-106">【인】 변경할 메서드의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="2bc7a-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="2bc7a-107">【인】 메서드 구현 기능을 지정하는 [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) 열거형값의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="2bc7a-107">[in] A combination of the values of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bc7a-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2bc7a-108">Requirements</span></span>  
 <span data-ttu-id="2bc7a-109">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2bc7a-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bc7a-110">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="2bc7a-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2bc7a-111">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="2bc7a-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2bc7a-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bc7a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bc7a-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2bc7a-113">See also</span></span>

- [<span data-ttu-id="2bc7a-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2bc7a-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="2bc7a-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2bc7a-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
