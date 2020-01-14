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
ms.openlocfilehash: d4055975287267d08d2c2224ff6ddaa39fca548d
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937789"
---
# <a name="imetadatatablesgetnextguid-method"></a><span data-ttu-id="3a32b-102">IMetaDataTables::GetNextGuid 메서드</span><span class="sxs-lookup"><span data-stu-id="3a32b-102">IMetaDataTables::GetNextGuid Method</span></span>
<span data-ttu-id="3a32b-103">현재 테이블 열에서 다음 GUID 값의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3a32b-103">Gets the index of the next GUID value in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a32b-104">구문</span><span class="sxs-lookup"><span data-stu-id="3a32b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextGuid (  
    [in]  ULONG   ixGuid,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a32b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3a32b-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="3a32b-106">진행 GUID 테이블 열의 인덱스 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3a32b-106">[in] The index value from a GUID table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="3a32b-107">제한이 다음 GUID 값의 인덱스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3a32b-107">[out] A pointer to the index of the next GUID value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a32b-108">주의</span><span class="sxs-lookup"><span data-stu-id="3a32b-108">Remarks</span></span>  

  <span data-ttu-id="3a32b-109">이 메서드를 사용 하는 것은 일관 된 결과를 반환 하지 않기 때문에 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3a32b-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="3a32b-110">GUID 테이블에 대 한 자세한 내용은 CLI (공용 언어 인프라) 설명서, 특히 "Partition II: 메타 데이터 정의 및 의미 체계"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3a32b-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="3a32b-111">설명서는 온라인으로 제공 됩니다. [ecma C# 및 공용 언어 인프라 표준](../../../standard/components.md#applicable-standards) 및 [표준 ECMA-335-CLI (공용 언어 인프라)](http://www.ecma-international.org/publications/standards/Ecma-335.htm)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3a32b-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a32b-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3a32b-112">Requirements</span></span>  
 <span data-ttu-id="3a32b-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a32b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a32b-114">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="3a32b-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3a32b-115">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a32b-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3a32b-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a32b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a32b-117">참조</span><span class="sxs-lookup"><span data-stu-id="3a32b-117">See also</span></span>

- [<span data-ttu-id="3a32b-118">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3a32b-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="3a32b-119">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3a32b-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
