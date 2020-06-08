---
title: IMetaDataTables::GetNumTables 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNumTables
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNumTables
helpviewer_keywords:
- GetNumTables method [.NET Framework metadata]
- IMetaDataTables::GetNumTables method [.NET Framework metadata]
ms.assetid: 8196f2a3-bbf2-45d3-a6cd-74502c356644
topic_type:
- apiref
ms.openlocfilehash: df02def0c14beb4e9ffd1b9260002767586a59b5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490200"
---
# <a name="imetadatatablesgetnumtables-method"></a><span data-ttu-id="8be61-102">IMetaDataTables::GetNumTables 메서드</span><span class="sxs-lookup"><span data-stu-id="8be61-102">IMetaDataTables::GetNumTables Method</span></span>
<span data-ttu-id="8be61-103">현재 인스턴스의 범위에 있는 테이블 수를 가져옵니다 `IMetaDataTables` .</span><span class="sxs-lookup"><span data-stu-id="8be61-103">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8be61-104">구문</span><span class="sxs-lookup"><span data-stu-id="8be61-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNumTables (  
    [out]  ULONG   *pcTables  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8be61-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8be61-105">Parameters</span></span>  
 `pcTables`  
 <span data-ttu-id="8be61-106">제한이 현재 인스턴스 범위의 테이블 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8be61-106">[out] A pointer to the number of tables in the current instance scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8be61-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8be61-107">Requirements</span></span>  
 <span data-ttu-id="8be61-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8be61-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8be61-109">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="8be61-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8be61-110">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8be61-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8be61-111">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8be61-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8be61-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8be61-112">See also</span></span>

- [<span data-ttu-id="8be61-113">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8be61-113">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="8be61-114">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8be61-114">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
