---
description: '자세히 알아보기: IMetaDataTables:: GetGuid 메서드'
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
ms.openlocfilehash: 9c3b8b11bb2f6a1abc3c55d953e1cbfbd7ee8622
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688171"
---
# <a name="imetadatatablesgetguid-method"></a><span data-ttu-id="d3781-103">IMetaDataTables::GetGuid 메서드</span><span class="sxs-lookup"><span data-stu-id="d3781-103">IMetaDataTables::GetGuid Method</span></span>

<span data-ttu-id="d3781-104">지정 된 인덱스의 행에서 GUID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d3781-104">Gets a GUID from the row at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3781-105">구문</span><span class="sxs-lookup"><span data-stu-id="d3781-105">Syntax</span></span>  
  
```cpp  
HRESULT GetGuid (
    [in]  ULONG       ixGuid,  
    [out] const GUID  **ppGUID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3781-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d3781-106">Parameters</span></span>  

 `ixGuid`  
 <span data-ttu-id="d3781-107">진행 GUID를 가져올 행의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="d3781-107">[in] The index of the row from which to get the GUID.</span></span>  
  
 `ppGuid`  
 <span data-ttu-id="d3781-108">제한이 GUID에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d3781-108">[out] A pointer to a pointer to the GUID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3781-109">설명</span><span class="sxs-lookup"><span data-stu-id="d3781-109">Remarks</span></span>  

  <span data-ttu-id="d3781-110">이 메서드를 사용 하는 것은 일관 된 결과를 반환 하지 않기 때문에 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d3781-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="d3781-111">GUID 테이블에 대 한 자세한 내용은 CLI (공용 언어 인프라) 설명서, 특히 "Partition II: 메타 데이터 정의 및 의미 체계"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d3781-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="d3781-112">설명서는 온라인으로 제공 됩니다. [Ecma c # 및 공용 언어 인프라 표준](../../../standard/components.md#applicable-standards) 및 [표준 ECMA-335-CLI (공용 언어 인프라)](http://www.ecma-international.org/publications/standards/Ecma-335.htm)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d3781-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3781-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d3781-113">Requirements</span></span>  

 <span data-ttu-id="d3781-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3781-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3781-115">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="d3781-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d3781-116">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3781-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d3781-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3781-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3781-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d3781-118">See also</span></span>

- [<span data-ttu-id="d3781-119">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d3781-119">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="d3781-120">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d3781-120">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
