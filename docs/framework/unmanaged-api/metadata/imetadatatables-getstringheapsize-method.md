---
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
ms.openlocfilehash: e3f6afaa79b7b299fa374c8220f5c2c3ad545ac9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672565"
---
# <a name="imetadatatablesgetstringheapsize-method"></a><span data-ttu-id="4d326-102">IMetaDataTables::GetStringHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="4d326-102">IMetaDataTables::GetStringHeapSize Method</span></span>

<span data-ttu-id="4d326-103">문자열 힙의 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4d326-103">Gets the size, in bytes, of the string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d326-104">구문</span><span class="sxs-lookup"><span data-stu-id="4d326-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStringHeapSize (  
    [out] ULONG   *pcbStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d326-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4d326-105">Parameters</span></span>  

 `pcbStrings`  
 <span data-ttu-id="4d326-106">제한이 문자열 힙의 크기 (바이트)에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4d326-106">[out] A pointer to the size, in bytes, of the string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d326-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4d326-107">Requirements</span></span>  

 <span data-ttu-id="4d326-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4d326-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d326-109">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="4d326-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4d326-110">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d326-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4d326-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d326-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d326-112">참조</span><span class="sxs-lookup"><span data-stu-id="4d326-112">See also</span></span>

- [<span data-ttu-id="4d326-113">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4d326-113">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="4d326-114">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4d326-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
