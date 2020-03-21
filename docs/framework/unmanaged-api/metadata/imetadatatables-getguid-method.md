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
ms.openlocfilehash: 57df124f15f78daad053d9634e1baa969a65cc35
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175280"
---
# <a name="imetadatatablesgetguid-method"></a><span data-ttu-id="81838-102">IMetaDataTables::GetGuid 메서드</span><span class="sxs-lookup"><span data-stu-id="81838-102">IMetaDataTables::GetGuid Method</span></span>
<span data-ttu-id="81838-103">지정된 인덱스의 행에서 GUID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="81838-103">Gets a GUID from the row at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81838-104">구문</span><span class="sxs-lookup"><span data-stu-id="81838-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGuid (
    [in]  ULONG       ixGuid,  
    [out] const GUID  **ppGUID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81838-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="81838-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="81838-106">【인】 GUID를 받을 행의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="81838-106">[in] The index of the row from which to get the GUID.</span></span>  
  
 `ppGuid`  
 <span data-ttu-id="81838-107">【아웃】 GUID에 대한 포인터에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="81838-107">[out] A pointer to a pointer to the GUID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81838-108">설명</span><span class="sxs-lookup"><span data-stu-id="81838-108">Remarks</span></span>  

  <span data-ttu-id="81838-109">일관된 결과를 반환하지 않으므로 이 메서드를 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="81838-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="81838-110">GUID 테이블에 대한 자세한 내용은 CLI(공통 언어 인프라) 설명서, 특히 "파티션 II: 메타데이터 정의 및 의미 체계"를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="81838-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="81838-111">이 설명서는 온라인으로 사용할 수 있습니다. [ECMA C# 및 공통 언어 인프라 표준](../../../standard/components.md#applicable-standards) 및 표준 [ECMA-335 - 공통 언어 인프라(CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm)참조.</span><span class="sxs-lookup"><span data-stu-id="81838-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81838-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="81838-112">Requirements</span></span>  
 <span data-ttu-id="81838-113">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="81838-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81838-114">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="81838-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="81838-115">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="81838-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="81838-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81838-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81838-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="81838-117">See also</span></span>

- [<span data-ttu-id="81838-118">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="81838-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="81838-119">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="81838-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
