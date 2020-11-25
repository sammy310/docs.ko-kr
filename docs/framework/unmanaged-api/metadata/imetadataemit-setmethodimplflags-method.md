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
ms.openlocfilehash: 486d545413337f6696bd9f21c516466fc3747256
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730359"
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="969d3-102">IMetaDataEmit::SetMethodImplFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="969d3-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>

<span data-ttu-id="969d3-103">지정 된 토큰이 참조 하는 상속 된 메서드 구현의 메타 데이터 서명을 설정 하거나 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="969d3-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="969d3-104">구문</span><span class="sxs-lookup"><span data-stu-id="969d3-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodImplFlags (
    [in]  mdMethodDef   md,
    [in]  DWORD         dwImplFlags
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="969d3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="969d3-105">Parameters</span></span>  

 `md`  
 <span data-ttu-id="969d3-106">진행 변경할 메서드의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="969d3-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="969d3-107">진행 메서드 구현 기능을 지정 하는 [Cormethodimpl](cormethodimpl-enumeration.md) 열거형 값의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="969d3-107">[in] A combination of the values of the [CorMethodImpl](cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="969d3-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="969d3-108">Requirements</span></span>  

 <span data-ttu-id="969d3-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="969d3-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="969d3-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="969d3-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="969d3-111">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="969d3-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="969d3-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="969d3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="969d3-113">참조</span><span class="sxs-lookup"><span data-stu-id="969d3-113">See also</span></span>

- [<span data-ttu-id="969d3-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="969d3-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="969d3-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="969d3-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
