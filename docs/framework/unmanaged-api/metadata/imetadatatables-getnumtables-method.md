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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b9ffd9ab9ddb95945744ecf210d0ae1d9d9812ec
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59125829"
---
# <a name="imetadatatablesgetnumtables-method"></a><span data-ttu-id="28323-102">IMetaDataTables::GetNumTables 메서드</span><span class="sxs-lookup"><span data-stu-id="28323-102">IMetaDataTables::GetNumTables Method</span></span>
<span data-ttu-id="28323-103">현재 범위에서 테이블의 수를 가져옵니다 `IMetaDataTables` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="28323-103">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28323-104">구문</span><span class="sxs-lookup"><span data-stu-id="28323-104">Syntax</span></span>  
  
```  
HRESULT GetNumTables (  
    [out]  ULONG   *pcTables  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28323-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="28323-105">Parameters</span></span>  
 `pcTables`  
 <span data-ttu-id="28323-106">[out] 현재 인스턴스 범위에 있는 테이블의 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="28323-106">[out] A pointer to the number of tables in the current instance scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28323-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="28323-107">Requirements</span></span>  
 <span data-ttu-id="28323-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="28323-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28323-109">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="28323-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="28323-110">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="28323-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="28323-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28323-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28323-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="28323-112">See also</span></span>

- [<span data-ttu-id="28323-113">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="28323-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="28323-114">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="28323-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
