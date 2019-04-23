---
title: IMetaDataTables::GetNextUserString 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextUserString
helpviewer_keywords:
- GetNextUserString method [.NET Framework metadata]
- IMetaDataTables::GetNextUserString method [.NET Framework metadata]
ms.assetid: b7cb40ee-67b7-4f4e-8dcc-ee7ac8bc986b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3ce6cfd6a331c9d9695f65eb3a670305de38d010
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59191183"
---
# <a name="imetadatatablesgetnextuserstring-method"></a><span data-ttu-id="27777-102">IMetaDataTables::GetNextUserString 메서드</span><span class="sxs-lookup"><span data-stu-id="27777-102">IMetaDataTables::GetNextUserString Method</span></span>
<span data-ttu-id="27777-103">현재 테이블 열에 다음 하드 코드 된 문자열을 포함 하는 행의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="27777-103">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27777-104">구문</span><span class="sxs-lookup"><span data-stu-id="27777-104">Syntax</span></span>  
  
```  
HRESULT GetNextUserString (  
    [in]  ULONG   ixUserString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27777-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="27777-105">Parameters</span></span>  
 `ixUserString`  
 <span data-ttu-id="27777-106">[in] 현재 문자열 열을 인덱스 값입니다.</span><span class="sxs-lookup"><span data-stu-id="27777-106">[in] An index value from the current string column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="27777-107">[out] 열에 다음 문자열의 행 인덱스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="27777-107">[out] A pointer to the row index of the next string in the column.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="27777-108">설명</span><span class="sxs-lookup"><span data-stu-id="27777-108">Remarks</span></span>  
 <span data-ttu-id="27777-109">바람직하지 않습니다이 메서드를 사용 하 여 일관 된 결과 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27777-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="27777-110">GUID 테이블에 대 한 자세한 내용은 공용 언어 인프라 (CLI), 특히 "파티션 II: 메타 데이터 정 및 의미 체계 "입니다.</span><span class="sxs-lookup"><span data-stu-id="27777-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="27777-111">이 설명서는 온라인으로 제공됩니다. MSDN의 [ECMA C# 및 공용 언어 인프라 표준](https://go.microsoft.com/fwlink/?LinkID=99212) 및 Ecma International 웹 사이트의 [표준 ECMA-335 - CLI(공용 언어 인프라)](https://go.microsoft.com/fwlink/?LinkID=65552)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="27777-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27777-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="27777-112">Requirements</span></span>  
 <span data-ttu-id="27777-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="27777-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27777-114">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="27777-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="27777-115">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="27777-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="27777-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27777-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27777-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="27777-117">See also</span></span>

- [<span data-ttu-id="27777-118">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="27777-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="27777-119">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="27777-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
