---
description: '자세히 알아보기: IMetaDataEmit:: SaveToMemory 메서드'
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
ms.openlocfilehash: b5fbca2c3ce06398de72bf2690108077545fef9c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745803"
---
# <a name="imetadataemitsavetomemory-method"></a><span data-ttu-id="15261-103">IMetaDataEmit::SaveToMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="15261-103">IMetaDataEmit::SaveToMemory Method</span></span>

<span data-ttu-id="15261-104">현재 범위에 있는 모든 메타 데이터를 지정 된 메모리 영역에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="15261-104">Saves all metadata in the current scope to the specified area of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15261-105">구문</span><span class="sxs-lookup"><span data-stu-id="15261-105">Syntax</span></span>  
  
```cpp  
HRESULT SaveToMemory (
    [out]  void        *pbData,
    [in]   ULONG       cbData
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15261-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="15261-106">Parameters</span></span>  

 `pbData`  
 <span data-ttu-id="15261-107">제한이 메타 데이터 작성을 시작할 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="15261-107">[out] The address at which to begin writing metadata.</span></span>  
  
 `cbData`  
 <span data-ttu-id="15261-108">진행 할당 된 메모리의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="15261-108">[in] The size, in bytes, of the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15261-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="15261-109">Requirements</span></span>  

 <span data-ttu-id="15261-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="15261-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15261-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="15261-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="15261-112">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15261-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15261-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15261-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15261-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="15261-114">See also</span></span>

- [<span data-ttu-id="15261-115">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15261-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="15261-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15261-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
