---
title: IMetaDataTables::GetGuid 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetGuid
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetGuid
helpviewer_keywords:
- GetGuid method [.NET Framework metadata]
- IMetaDataTables::GetGuid method [.NET Framework metadata]
ms.assetid: a3546316-e24d-417f-9909-e45d42c9d471
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 94df2192b0b02f6cf0e068cb554afc6e7f9ec74d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486942"
---
# <a name="imetadatatablesgetguid-method"></a><span data-ttu-id="99725-102">IMetaDataTables::GetGuid 메서드</span><span class="sxs-lookup"><span data-stu-id="99725-102">IMetaDataTables::GetGuid Method</span></span>
<span data-ttu-id="99725-103">지정된 된 인덱스에서 행의 GUID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="99725-103">Gets a GUID from the row at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99725-104">구문</span><span class="sxs-lookup"><span data-stu-id="99725-104">Syntax</span></span>  
  
```  
HRESULT GetGuid (   
    [in]  ULONG       ixGuid,  
    [out] const GUID  **ppGUID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99725-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="99725-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="99725-106">[in] GUID를 가져올 행의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="99725-106">[in] The index of the row from which to get the GUID.</span></span>  
  
 `ppGuid`  
 <span data-ttu-id="99725-107">[out] GUID에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="99725-107">[out] A pointer to a pointer to the GUID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99725-108">설명</span><span class="sxs-lookup"><span data-stu-id="99725-108">Remarks</span></span>  
 <span data-ttu-id="99725-109">바람직하지 않습니다이 메서드를 사용 하 여 일관 된 결과 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99725-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="99725-110">GUID 테이블에 대 한 자세한 내용은 공용 언어 인프라 (CLI), 특히 "파티션 II: 메타 데이터 정 및 의미 체계 "입니다.</span><span class="sxs-lookup"><span data-stu-id="99725-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="99725-111">이 설명서는 온라인으로 제공됩니다. MSDN의 [ECMA C# 및 공용 언어 인프라 표준](https://go.microsoft.com/fwlink/?LinkID=99212) 및 Ecma International 웹 사이트의 [표준 ECMA-335 - CLI(공용 언어 인프라)](https://go.microsoft.com/fwlink/?LinkID=65552)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99725-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99725-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="99725-112">Requirements</span></span>  
 <span data-ttu-id="99725-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="99725-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99725-114">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="99725-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="99725-115">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="99725-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="99725-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99725-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99725-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="99725-117">See also</span></span>
- [<span data-ttu-id="99725-118">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="99725-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="99725-119">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="99725-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
