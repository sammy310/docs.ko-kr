---
title: IMetaDataEmit2::SaveDeltaToMemory 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDeltaToMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToMemory
helpviewer_keywords:
- SaveDeltaToMemory method [.NET Framework metadata]
- IMetaDataEmit2::SaveDeltaToMemory method [.NET Framework metadata]
ms.assetid: e2146726-0084-4c9e-a2d2-e8d461b13b21
topic_type:
- apiref
ms.openlocfilehash: a4dbe090987248ef77ce371b5bc6fb42d898f726
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705412"
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="899a3-102">IMetaDataEmit2::SaveDeltaToMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="899a3-102">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>

<span data-ttu-id="899a3-103">현재 편집 하며 계속 하기 세션의 변경 내용을 메모리로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="899a3-103">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="899a3-104">구문</span><span class="sxs-lookup"><span data-stu-id="899a3-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,
    [in]  ULONG       cbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="899a3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="899a3-105">Parameters</span></span>  

 `pbData`  
 <span data-ttu-id="899a3-106">제한이 메타 데이터 델타를 쓰기 시작할 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="899a3-106">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="899a3-107">진행 변경 내용의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="899a3-107">[in] The size of the changes.</span></span> <span data-ttu-id="899a3-108">[IMetaDataEmit2:: GetDeltaSaveSize](imetadataemit2-getdeltasavesize-method.md) 를 사용 하 여 크기를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="899a3-108">Use [IMetaDataEmit2::GetDeltaSaveSize](imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="899a3-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="899a3-109">Requirements</span></span>  

 <span data-ttu-id="899a3-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="899a3-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="899a3-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="899a3-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="899a3-112">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="899a3-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="899a3-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="899a3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="899a3-114">참조</span><span class="sxs-lookup"><span data-stu-id="899a3-114">See also</span></span>

- [<span data-ttu-id="899a3-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="899a3-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="899a3-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="899a3-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
