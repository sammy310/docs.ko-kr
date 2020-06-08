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
ms.openlocfilehash: 3638ab12fc311ece9f24608cbb36219e10f01f2d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501177"
---
# <a name="imetadatatablesgettableindex-method"></a><span data-ttu-id="349a7-102">IMetaDataTables::GetTableIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="349a7-102">IMetaDataTables::GetTableIndex Method</span></span>
<span data-ttu-id="349a7-103">지정 된 토큰이 참조 하는 테이블의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="349a7-103">Gets the index for the table referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="349a7-104">구문</span><span class="sxs-lookup"><span data-stu-id="349a7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTableIndex (  
    [in]  ULONG   token,  
    [out] ULONG   *pixTbl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="349a7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="349a7-105">Parameters</span></span>  
 `token`  
 <span data-ttu-id="349a7-106">진행 테이블을 참조 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="349a7-106">[in] The token that references the table.</span></span>  
  
 `pixTbl`  
 <span data-ttu-id="349a7-107">제한이 참조 된 테이블에 대해 반환 된 인덱스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="349a7-107">[out] A pointer to the returned index for the referenced table.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="349a7-108">설명</span><span class="sxs-lookup"><span data-stu-id="349a7-108">Remarks</span></span>  
 <span data-ttu-id="349a7-109">이 메서드를 사용 하는 것은 일관 된 결과를 반환 하지 않기 때문에 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="349a7-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="349a7-110">GUID 테이블에 대 한 자세한 내용은 CLI (공용 언어 인프라) 설명서, 특히 "Partition II: 메타 데이터 정의 및 의미 체계"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="349a7-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="349a7-111">설명서는 온라인으로 제공 됩니다. [Ecma c # 및 공용 언어 인프라 표준](../../../standard/components.md#applicable-standards) 및 [표준 ECMA-335-CLI (공용 언어 인프라)](http://www.ecma-international.org/publications/standards/Ecma-335.htm)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="349a7-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="349a7-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="349a7-112">Requirements</span></span>  
 <span data-ttu-id="349a7-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="349a7-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="349a7-114">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="349a7-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="349a7-115">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="349a7-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="349a7-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="349a7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="349a7-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="349a7-117">See also</span></span>

- [<span data-ttu-id="349a7-118">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="349a7-118">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="349a7-119">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="349a7-119">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
