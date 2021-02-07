---
description: '자세히 알아보기: IMetaDataTables:: GetStringHeapSize 메서드'
title: IMetaDataTables::GetStringHeapSize 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetStringHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetStringHeapSize method [.NET Framework metadata]
- GetStringHeapSize method [.NET Framework metadata]
ms.assetid: ed8f6335-81f5-4c09-81a9-2a909fc530c9
topic_type:
- apiref
ms.openlocfilehash: 0ec9f4e2768cc78163db67bc9099fc9cafae8c8c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687781"
---
# <a name="imetadatatablesgetstringheapsize-method"></a><span data-ttu-id="11b3f-103">IMetaDataTables::GetStringHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="11b3f-103">IMetaDataTables::GetStringHeapSize Method</span></span>

<span data-ttu-id="11b3f-104">문자열 힙의 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="11b3f-104">Gets the size, in bytes, of the string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11b3f-105">구문</span><span class="sxs-lookup"><span data-stu-id="11b3f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStringHeapSize (  
    [out] ULONG   *pcbStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11b3f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="11b3f-106">Parameters</span></span>  

 `pcbStrings`  
 <span data-ttu-id="11b3f-107">제한이 문자열 힙의 크기 (바이트)에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="11b3f-107">[out] A pointer to the size, in bytes, of the string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11b3f-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="11b3f-108">Requirements</span></span>  

 <span data-ttu-id="11b3f-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="11b3f-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11b3f-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="11b3f-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="11b3f-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11b3f-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="11b3f-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11b3f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11b3f-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11b3f-113">See also</span></span>

- [<span data-ttu-id="11b3f-114">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="11b3f-114">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="11b3f-115">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="11b3f-115">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
