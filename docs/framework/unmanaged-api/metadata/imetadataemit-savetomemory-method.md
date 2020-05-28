---
title: IMetaDataEmit::SaveToMemory 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToMemory
helpviewer_keywords:
- IMetaDataEmit::SaveToMemory method [.NET Framework metadata]
- SaveToMemory method [.NET Framework metadata]
ms.assetid: d5237628-2675-45ed-a39e-65c0731b6a56
topic_type:
- apiref
ms.openlocfilehash: ccf82531eb1f78bcfc6762d10d53ffee59f30ad8
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003957"
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="fe647-102">IMetaDataEmit::SaveToMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="fe647-102">IMetaDataEmit::SaveToMemory Method</span></span>
<span data-ttu-id="fe647-103">현재 범위에 있는 모든 메타 데이터를 지정 된 메모리 영역에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe647-103">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe647-104">구문</span><span class="sxs-lookup"><span data-stu-id="fe647-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToMemory (
    [out]  void        *pbData,
    [in]   ULONG       cbData
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe647-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fe647-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="fe647-106">제한이 메타 데이터 작성을 시작할 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="fe647-106">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="fe647-107">진행 할당 된 메모리의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="fe647-107">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe647-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fe647-108">Requirements</span></span>  
 <span data-ttu-id="fe647-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fe647-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe647-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="fe647-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fe647-111">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe647-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fe647-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe647-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe647-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe647-113">See also</span></span>

- [<span data-ttu-id="fe647-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fe647-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="fe647-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fe647-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
