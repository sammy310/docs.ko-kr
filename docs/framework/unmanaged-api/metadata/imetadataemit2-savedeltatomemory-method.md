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
ms.openlocfilehash: 8a6f11996425c92d9b0e3123ee2d3a064739454b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492762"
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="a4a55-102">IMetaDataEmit2::SaveDeltaToMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="a4a55-102">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>
<span data-ttu-id="a4a55-103">현재 편집 하며 계속 하기 세션의 변경 내용을 메모리로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4a55-103">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4a55-104">구문</span><span class="sxs-lookup"><span data-stu-id="a4a55-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,
    [in]  ULONG       cbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4a55-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a4a55-105">Parameters</span></span>  
 `pbData`  
 <span data-ttu-id="a4a55-106">제한이 메타 데이터 델타를 쓰기 시작할 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="a4a55-106">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="a4a55-107">진행 변경 내용의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="a4a55-107">[in] The size of the changes.</span></span> <span data-ttu-id="a4a55-108">[IMetaDataEmit2:: GetDeltaSaveSize](imetadataemit2-getdeltasavesize-method.md) 를 사용 하 여 크기를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4a55-108">Use [IMetaDataEmit2::GetDeltaSaveSize](imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4a55-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a4a55-109">Requirements</span></span>  
 <span data-ttu-id="a4a55-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4a55-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4a55-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="a4a55-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a4a55-112">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4a55-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a4a55-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4a55-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4a55-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a4a55-114">See also</span></span>

- [<span data-ttu-id="a4a55-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4a55-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="a4a55-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4a55-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
