---
description: '자세히 알아보기: IMetaDataTables:: GetUserStringHeapSize 메서드'
title: IMetaDataTables::GetUserStringHeapSize 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetUserStringHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetUserStringHeapSize method [.NET Framework metadata]
- GetUserStringHeapSize method [.NET Framework metadata]
ms.assetid: cba9e4d6-9461-4420-9614-96ff7039ec9c
topic_type:
- apiref
ms.openlocfilehash: 7e6f3eed7803f52e6bde888852c4971900f0868c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687625"
---
# <a name="imetadatatablesgetuserstringheapsize-method"></a><span data-ttu-id="c2a7a-103">IMetaDataTables::GetUserStringHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="c2a7a-103">IMetaDataTables::GetUserStringHeapSize Method</span></span>

<span data-ttu-id="c2a7a-104">사용자 문자열 힙의 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c2a7a-104">Gets the size, in bytes, of the user string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2a7a-105">구문</span><span class="sxs-lookup"><span data-stu-id="c2a7a-105">Syntax</span></span>  
  
```cpp  
HRESULT GetUserStringHeapSize (  
    [out] ULONG   *pcbBlobs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2a7a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c2a7a-106">Parameters</span></span>  

 `pcbBlobs`  
 <span data-ttu-id="c2a7a-107">제한이 사용자 문자열 힙의 크기 (바이트)에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c2a7a-107">[out] A pointer to the size, in bytes, of the user string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2a7a-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c2a7a-108">Requirements</span></span>  

 <span data-ttu-id="c2a7a-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2a7a-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2a7a-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="c2a7a-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c2a7a-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2a7a-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c2a7a-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2a7a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2a7a-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c2a7a-113">See also</span></span>

- [<span data-ttu-id="c2a7a-114">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2a7a-114">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="c2a7a-115">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2a7a-115">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
