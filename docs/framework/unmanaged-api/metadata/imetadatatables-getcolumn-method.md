---
title: IMetaDataTables::GetColumn 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetColumn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumn
helpviewer_keywords:
- IMetaDataTables::GetColumn method [.NET Framework metadata]
- GetColumn method [.NET Framework metadata]
ms.assetid: 1032055b-cabb-45c5-a50e-7e853201b175
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 90ce56b3959c4768ef9cb6a9c551d53c5300a39e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59208360"
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="2b77f-102">IMetaDataTables::GetColumn 메서드</span><span class="sxs-lookup"><span data-stu-id="2b77f-102">IMetaDataTables::GetColumn Method</span></span>
<span data-ttu-id="2b77f-103">지정 된 열 및 지정된 된 테이블에서 행의 셀에 포함 된 값에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2b77f-103">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b77f-104">구문</span><span class="sxs-lookup"><span data-stu-id="2b77f-104">Syntax</span></span>  
  
```  
HRESULT GetColumn (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b77f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2b77f-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="2b77f-106">[in] 테이블의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="2b77f-106">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="2b77f-107">[in] 테이블의 열 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="2b77f-107">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="2b77f-108">[in] 테이블에서 행의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="2b77f-108">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="2b77f-109">[out] 셀의 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2b77f-109">[out] A pointer to the value in the cell.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b77f-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2b77f-110">Requirements</span></span>  
 <span data-ttu-id="2b77f-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2b77f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b77f-112">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2b77f-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2b77f-113">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="2b77f-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2b77f-114">**.NET framework 버전** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b77f-114">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b77f-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="2b77f-115">See also</span></span>

- [<span data-ttu-id="2b77f-116">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2b77f-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="2b77f-117">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2b77f-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
