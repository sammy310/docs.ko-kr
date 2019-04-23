---
title: IMetaDataTables::GetNextGuid 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextGuid
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextGuid
helpviewer_keywords:
- GetNextGuid method [.NET Framework metadata]
- IMetaDataTables::GetNextGuid method [.NET Framework metadata]
ms.assetid: 68f6ea4d-9112-4d6b-93d9-e34f1e2f2496
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b23e1d26d62012efe338eeb179db0e7ee17cd658
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110471"
---
# <a name="imetadatatablesgetnextguid-method"></a><span data-ttu-id="76acc-102">IMetaDataTables::GetNextGuid 메서드</span><span class="sxs-lookup"><span data-stu-id="76acc-102">IMetaDataTables::GetNextGuid Method</span></span>
<span data-ttu-id="76acc-103">현재 테이블 열에 다음 GUID 값의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="76acc-103">Gets the index of the next GUID value in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76acc-104">구문</span><span class="sxs-lookup"><span data-stu-id="76acc-104">Syntax</span></span>  
  
```  
HRESULT GetNextGuid (  
    [in]  ULONG   ixGuid,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76acc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="76acc-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="76acc-106">[in] GUID 테이블 열에서 인덱스 값입니다.</span><span class="sxs-lookup"><span data-stu-id="76acc-106">[in] The index value from a GUID table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="76acc-107">[out] 다음 GUID 값의 인덱스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="76acc-107">[out] A pointer to the index of the next GUID value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76acc-108">설명</span><span class="sxs-lookup"><span data-stu-id="76acc-108">Remarks</span></span>  
 <span data-ttu-id="76acc-109">바람직하지 않습니다이 메서드를 사용 하 여 일관 된 결과 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76acc-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="76acc-110">GUID 테이블에 대 한 자세한 내용은 공용 언어 인프라 (CLI), 특히 "파티션 II: 메타 데이터 정 및 의미 체계 "입니다.</span><span class="sxs-lookup"><span data-stu-id="76acc-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="76acc-111">이 설명서는 온라인으로 제공됩니다. MSDN의 [ECMA C# 및 공용 언어 인프라 표준](https://go.microsoft.com/fwlink/?LinkID=99212) 및 Ecma International 웹 사이트의 [표준 ECMA-335 - CLI(공용 언어 인프라)](https://go.microsoft.com/fwlink/?LinkID=65552)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76acc-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76acc-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="76acc-112">Requirements</span></span>  
 <span data-ttu-id="76acc-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="76acc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76acc-114">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="76acc-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="76acc-115">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="76acc-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="76acc-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76acc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76acc-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="76acc-117">See also</span></span>

- [<span data-ttu-id="76acc-118">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="76acc-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="76acc-119">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="76acc-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
