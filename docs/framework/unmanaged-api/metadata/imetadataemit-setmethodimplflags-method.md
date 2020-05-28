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
ms.openlocfilehash: a02456393680169ce33369ee5914f6c5216081c6
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009225"
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="b9e74-102">IMetaDataEmit::SetMethodImplFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="b9e74-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>
<span data-ttu-id="b9e74-103">지정 된 토큰이 참조 하는 상속 된 메서드 구현의 메타 데이터 서명을 설정 하거나 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e74-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9e74-104">구문</span><span class="sxs-lookup"><span data-stu-id="b9e74-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodImplFlags (
    [in]  mdMethodDef   md,
    [in]  DWORD         dwImplFlags
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9e74-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b9e74-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="b9e74-106">진행 변경할 메서드의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="b9e74-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="b9e74-107">진행 메서드 구현 기능을 지정 하는 [Cormethodimpl](cormethodimpl-enumeration.md) 열거형 값의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="b9e74-107">[in] A combination of the values of the [CorMethodImpl](cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9e74-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b9e74-108">Requirements</span></span>  
 <span data-ttu-id="b9e74-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b9e74-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9e74-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="b9e74-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b9e74-111">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9e74-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b9e74-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9e74-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9e74-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b9e74-113">See also</span></span>

- [<span data-ttu-id="b9e74-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b9e74-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="b9e74-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b9e74-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
