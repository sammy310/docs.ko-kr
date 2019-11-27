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
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="4ac0e-102">IMetaDataTables::GetRow 메서드</span><span class="sxs-lookup"><span data-stu-id="4ac0e-102">IMetaDataTables::GetRow Method</span></span>
<span data-ttu-id="4ac0e-103">지정 된 테이블 인덱스에 있는 테이블의 지정 된 행 인덱스에 있는 행을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4ac0e-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ac0e-104">구문</span><span class="sxs-lookup"><span data-stu-id="4ac0e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRow (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4ac0e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4ac0e-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="4ac0e-106">진행 행을 검색할 테이블의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="4ac0e-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="4ac0e-107">진행 가져올 행의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="4ac0e-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="4ac0e-108">제한이 행에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4ac0e-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4ac0e-109">주의</span><span class="sxs-lookup"><span data-stu-id="4ac0e-109">Remarks</span></span>  
 <span data-ttu-id="4ac0e-110">이 메서드를 사용 하는 것은 일관 된 결과를 반환 하지 않기 때문에 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4ac0e-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="4ac0e-111">GUID 테이블에 대 한 자세한 내용은 CLI (공용 언어 인프라) 설명서, 특히 "Partition II: 메타 데이터 정의 및 의미 체계"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4ac0e-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="4ac0e-112">이 설명서는 온라인으로 제공됩니다. MSDN의 [ECMA C# 및 공용 언어 인프라 표준](https://go.microsoft.com/fwlink/?LinkID=99212) 및 Ecma International 웹 사이트의 [표준 ECMA-335 - CLI(공용 언어 인프라)](https://go.microsoft.com/fwlink/?LinkID=65552)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ac0e-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4ac0e-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4ac0e-113">Requirements</span></span>  
 <span data-ttu-id="4ac0e-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4ac0e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ac0e-115">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="4ac0e-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4ac0e-116">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ac0e-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4ac0e-117">**.NET Framework 버전**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ac0e-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ac0e-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ac0e-118">See also</span></span>

- [<span data-ttu-id="4ac0e-119">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4ac0e-119">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="4ac0e-120">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4ac0e-120">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
