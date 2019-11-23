---
title: IMetaDataTables::GetRow 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetRow
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetRow
helpviewer_keywords:
- IMetaDataTables::GetRow method [.NET Framework metadata]
- GetRow method [.NET Framework metadata]
ms.assetid: a7408d51-0bce-45a2-b58f-da4660bbc039
topic_type:
- apiref
ms.openlocfilehash: 9973ef77a064dfe144d742d8cf12d8ae8dd2565f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447405"
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="ccd3a-102">IMetaDataTables::GetRow 메서드</span><span class="sxs-lookup"><span data-stu-id="ccd3a-102">IMetaDataTables::GetRow Method</span></span>
<span data-ttu-id="ccd3a-103">Gets the row at the specified row index, in the table at the specified table index.</span><span class="sxs-lookup"><span data-stu-id="ccd3a-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccd3a-104">구문</span><span class="sxs-lookup"><span data-stu-id="ccd3a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRow (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ccd3a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ccd3a-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="ccd3a-106">[in] The index of the table from which the row will be retrieved.</span><span class="sxs-lookup"><span data-stu-id="ccd3a-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="ccd3a-107">[in] The index of the row to get.</span><span class="sxs-lookup"><span data-stu-id="ccd3a-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="ccd3a-108">[out] A pointer to a pointer to the row.</span><span class="sxs-lookup"><span data-stu-id="ccd3a-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ccd3a-109">주의</span><span class="sxs-lookup"><span data-stu-id="ccd3a-109">Remarks</span></span>  
 <span data-ttu-id="ccd3a-110">We do not recommend the use of this method, because it does not return consistent results.</span><span class="sxs-lookup"><span data-stu-id="ccd3a-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="ccd3a-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span><span class="sxs-lookup"><span data-stu-id="ccd3a-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="ccd3a-112">이 설명서는 온라인으로 제공됩니다. MSDN의 [ECMA C# 및 공용 언어 인프라 표준](https://go.microsoft.com/fwlink/?LinkID=99212) 및 Ecma International 웹 사이트의 [표준 ECMA-335 - CLI(공용 언어 인프라)](https://go.microsoft.com/fwlink/?LinkID=65552)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ccd3a-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccd3a-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ccd3a-113">Requirements</span></span>  
 <span data-ttu-id="ccd3a-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ccd3a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccd3a-115">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ccd3a-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ccd3a-116">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ccd3a-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ccd3a-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccd3a-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccd3a-118">참조</span><span class="sxs-lookup"><span data-stu-id="ccd3a-118">See also</span></span>

- [<span data-ttu-id="ccd3a-119">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ccd3a-119">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="ccd3a-120">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ccd3a-120">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
