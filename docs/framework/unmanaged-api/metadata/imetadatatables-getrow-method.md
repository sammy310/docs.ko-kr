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
ms.openlocfilehash: 71f6c496816fec1a7537f5ccdfdc1b47d17da871
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177110"
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="74576-102">IMetaDataTables::GetRow 메서드</span><span class="sxs-lookup"><span data-stu-id="74576-102">IMetaDataTables::GetRow Method</span></span>
<span data-ttu-id="74576-103">지정된 테이블 인덱스의 테이블에서 지정된 행 인덱스에서 행을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="74576-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74576-104">구문</span><span class="sxs-lookup"><span data-stu-id="74576-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRow (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74576-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="74576-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="74576-106">【인】 행을 검색할 테이블의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="74576-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="74576-107">【인】 얻을 행의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="74576-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="74576-108">【아웃】 행에 대한 포인터에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="74576-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="74576-109">설명</span><span class="sxs-lookup"><span data-stu-id="74576-109">Remarks</span></span>  

  <span data-ttu-id="74576-110">일관된 결과를 반환하지 않으므로 이 메서드를 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="74576-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="74576-111">GUID 테이블에 대한 자세한 내용은 CLI(공통 언어 인프라) 설명서, 특히 "파티션 II: 메타데이터 정의 및 의미 체계"를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="74576-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="74576-112">이 설명서는 온라인으로 사용할 수 있습니다. [ECMA C# 및 공통 언어 인프라 표준](../../../standard/components.md#applicable-standards) 및 표준 [ECMA-335 - 공통 언어 인프라(CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm)참조.</span><span class="sxs-lookup"><span data-stu-id="74576-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74576-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="74576-113">Requirements</span></span>  
 <span data-ttu-id="74576-114">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="74576-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74576-115">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="74576-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="74576-116">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="74576-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="74576-117">**.NET 프레임워크 버전**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74576-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74576-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="74576-118">See also</span></span>

- [<span data-ttu-id="74576-119">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="74576-119">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="74576-120">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="74576-120">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
