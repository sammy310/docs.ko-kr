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
ms.openlocfilehash: 1f0c52efd4b55d19cbd7b2407c4b2d7c893b1009
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436092"
---
# <a name="imetadatatablesgetguid-method"></a><span data-ttu-id="0d49f-102">IMetaDataTables::GetGuid 메서드</span><span class="sxs-lookup"><span data-stu-id="0d49f-102">IMetaDataTables::GetGuid Method</span></span>
<span data-ttu-id="0d49f-103">지정 된 인덱스의 행에서 GUID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0d49f-103">Gets a GUID from the row at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d49f-104">구문</span><span class="sxs-lookup"><span data-stu-id="0d49f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGuid (   
    [in]  ULONG       ixGuid,  
    [out] const GUID  **ppGUID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d49f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0d49f-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="0d49f-106">진행 GUID를 가져올 행의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="0d49f-106">[in] The index of the row from which to get the GUID.</span></span>  
  
 `ppGuid`  
 <span data-ttu-id="0d49f-107">제한이 GUID에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0d49f-107">[out] A pointer to a pointer to the GUID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0d49f-108">주의</span><span class="sxs-lookup"><span data-stu-id="0d49f-108">Remarks</span></span>  
 <span data-ttu-id="0d49f-109">이 메서드를 사용 하는 것은 일관 된 결과를 반환 하지 않기 때문에 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0d49f-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="0d49f-110">GUID 테이블에 대 한 자세한 내용은 CLI (공용 언어 인프라) 설명서, 특히 "Partition II: 메타 데이터 정의 및 의미 체계"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0d49f-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="0d49f-111">이 설명서는 온라인으로 제공됩니다. MSDN의 [ECMA C# 및 공용 언어 인프라 표준](https://go.microsoft.com/fwlink/?LinkID=99212) 및 Ecma International 웹 사이트의 [표준 ECMA-335 - CLI(공용 언어 인프라)](https://go.microsoft.com/fwlink/?LinkID=65552)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d49f-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d49f-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0d49f-112">Requirements</span></span>  
 <span data-ttu-id="0d49f-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d49f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d49f-114">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="0d49f-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0d49f-115">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d49f-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0d49f-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d49f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d49f-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0d49f-117">See also</span></span>

- [<span data-ttu-id="0d49f-118">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0d49f-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="0d49f-119">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0d49f-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
