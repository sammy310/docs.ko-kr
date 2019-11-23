---
title: IMetaDataTables::GetTableIndex 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableIndex
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableIndex
helpviewer_keywords:
- GetTableIndex method [.NET Framework metadata]
- IMetaDataTables::GetTableIndex method [.NET Framework metadata]
ms.assetid: c6ec3800-e0d9-4387-afb8-ddc0b818114c
topic_type:
- apiref
ms.openlocfilehash: 48c38288e960ff2e1fe21f30b6eceae8eeaac2da
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434846"
---
# <a name="imetadatatablesgettableindex-method"></a><span data-ttu-id="13f1e-102">IMetaDataTables::GetTableIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="13f1e-102">IMetaDataTables::GetTableIndex Method</span></span>
<span data-ttu-id="13f1e-103">Gets the index for the table referenced by the specified token.</span><span class="sxs-lookup"><span data-stu-id="13f1e-103">Gets the index for the table referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13f1e-104">구문</span><span class="sxs-lookup"><span data-stu-id="13f1e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTableIndex (  
    [in]  ULONG   token,  
    [out] ULONG   *pixTbl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13f1e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="13f1e-105">Parameters</span></span>  
 `token`  
 <span data-ttu-id="13f1e-106">[in] The token that references the table.</span><span class="sxs-lookup"><span data-stu-id="13f1e-106">[in] The token that references the table.</span></span>  
  
 `pixTbl`  
 <span data-ttu-id="13f1e-107">[out] A pointer to the returned index for the referenced table.</span><span class="sxs-lookup"><span data-stu-id="13f1e-107">[out] A pointer to the returned index for the referenced table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13f1e-108">주의</span><span class="sxs-lookup"><span data-stu-id="13f1e-108">Remarks</span></span>  
 <span data-ttu-id="13f1e-109">We do not recommend the use of this method, because it does not return consistent results.</span><span class="sxs-lookup"><span data-stu-id="13f1e-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="13f1e-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span><span class="sxs-lookup"><span data-stu-id="13f1e-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="13f1e-111">이 설명서는 온라인으로 제공됩니다. MSDN의 [ECMA C# 및 공용 언어 인프라 표준](https://go.microsoft.com/fwlink/?LinkID=99212) 및 Ecma International 웹 사이트의 [표준 ECMA-335 - CLI(공용 언어 인프라)](https://go.microsoft.com/fwlink/?LinkID=65552)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="13f1e-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13f1e-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="13f1e-112">Requirements</span></span>  
 <span data-ttu-id="13f1e-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="13f1e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13f1e-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="13f1e-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="13f1e-115">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="13f1e-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="13f1e-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13f1e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13f1e-117">참조</span><span class="sxs-lookup"><span data-stu-id="13f1e-117">See also</span></span>

- [<span data-ttu-id="13f1e-118">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="13f1e-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="13f1e-119">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="13f1e-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
