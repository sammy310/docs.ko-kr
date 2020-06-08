---
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
ms.openlocfilehash: 1aea017f17e29544e9288e1f57e6f84f9a2f6dae
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501107"
---
# <a name="imetadatatablesgetuserstringheapsize-method"></a><span data-ttu-id="109e2-102">IMetaDataTables::GetUserStringHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="109e2-102">IMetaDataTables::GetUserStringHeapSize Method</span></span>
<span data-ttu-id="109e2-103">사용자 문자열 힙의 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="109e2-103">Gets the size, in bytes, of the user string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="109e2-104">구문</span><span class="sxs-lookup"><span data-stu-id="109e2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserStringHeapSize (  
    [out] ULONG   *pcbBlobs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="109e2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="109e2-105">Parameters</span></span>  
 `pcbBlobs`  
 <span data-ttu-id="109e2-106">제한이 사용자 문자열 힙의 크기 (바이트)에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="109e2-106">[out] A pointer to the size, in bytes, of the user string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="109e2-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="109e2-107">Requirements</span></span>  
 <span data-ttu-id="109e2-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="109e2-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="109e2-109">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="109e2-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="109e2-110">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="109e2-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="109e2-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="109e2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="109e2-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="109e2-112">See also</span></span>

- [<span data-ttu-id="109e2-113">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="109e2-113">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="109e2-114">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="109e2-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
