---
title: IMetaDataEmit::SetFieldRVA 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldRVA
helpviewer_keywords:
- IMetaDataEmit::SetFieldRVA method [.NET Framework metadata]
- SetFieldRVA method [.NET Framework metadata]
ms.assetid: 6dc37f9d-87ee-4cb3-9216-ced600184ce8
topic_type:
- apiref
ms.openlocfilehash: 8468b0e7faa520fe2d27e17674af5503871d3b62
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730385"
---
# <a name="imetadataemitsetfieldrva-method"></a><span data-ttu-id="3e196-102">IMetaDataEmit::SetFieldRVA 메서드</span><span class="sxs-lookup"><span data-stu-id="3e196-102">IMetaDataEmit::SetFieldRVA Method</span></span>

<span data-ttu-id="3e196-103">지정 된 토큰이 참조 하는 필드의 상대 가상 주소에 대 한 전역 변수 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e196-103">Sets a global variable value for the relative virtual address of the field referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e196-104">구문</span><span class="sxs-lookup"><span data-stu-id="3e196-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldRVA (
    [in]  mdFieldDef  fd,
    [in]  ULONG       ulRVA
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e196-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3e196-105">Parameters</span></span>  

 `fd`  
 <span data-ttu-id="3e196-106">진행 대상 필드의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="3e196-106">[in] The token for the target field.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="3e196-107">진행 코드 또는 데이터 영역의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="3e196-107">[in] The address of a code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e196-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3e196-108">Requirements</span></span>  

 <span data-ttu-id="3e196-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3e196-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e196-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="3e196-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3e196-111">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e196-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3e196-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e196-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e196-113">참조</span><span class="sxs-lookup"><span data-stu-id="3e196-113">See also</span></span>

- [<span data-ttu-id="3e196-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3e196-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="3e196-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3e196-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
