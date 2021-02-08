---
description: '자세히 알아보기: IMetaDataEmit2:: SaveDeltaToMemory 메서드'
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
ms.openlocfilehash: 3ef01889df6dede85947508ca08635c95d655666
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771758"
---
# <a name="imetadataemit2savedeltatomemory-method"></a><span data-ttu-id="8879a-103">IMetaDataEmit2::SaveDeltaToMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="8879a-103">IMetaDataEmit2::SaveDeltaToMemory Method</span></span>

<span data-ttu-id="8879a-104">현재 편집 하며 계속 하기 세션의 변경 내용을 메모리로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8879a-104">Saves changes from the current edit-and-continue session to memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8879a-105">구문</span><span class="sxs-lookup"><span data-stu-id="8879a-105">Syntax</span></span>  
  
```cpp  
HRESULT SaveDeltaToMemory (  
    [out] void        *pbData,
    [in]  ULONG       cbData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8879a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8879a-106">Parameters</span></span>  

 `pbData`  
 <span data-ttu-id="8879a-107">제한이 메타 데이터 델타를 쓰기 시작할 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="8879a-107">[out] The address at which to begin writing the metadata delta.</span></span>  
  
 `cbData`  
 <span data-ttu-id="8879a-108">진행 변경 내용의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="8879a-108">[in] The size of the changes.</span></span> <span data-ttu-id="8879a-109">[IMetaDataEmit2:: GetDeltaSaveSize](imetadataemit2-getdeltasavesize-method.md) 를 사용 하 여 크기를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8879a-109">Use [IMetaDataEmit2::GetDeltaSaveSize](imetadataemit2-getdeltasavesize-method.md) to determine the size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8879a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8879a-110">Requirements</span></span>  

 <span data-ttu-id="8879a-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8879a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8879a-112">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="8879a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8879a-113">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8879a-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8879a-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8879a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8879a-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8879a-115">See also</span></span>

- [<span data-ttu-id="8879a-116">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8879a-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="8879a-117">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8879a-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
