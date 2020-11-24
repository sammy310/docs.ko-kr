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
ms.openlocfilehash: bb53d980a7b2121854748d5117bc539fed125163
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680367"
---
# <a name="imetadatatablesgetnextuserstring-method"></a><span data-ttu-id="46d41-102">IMetaDataTables::GetNextUserString 메서드</span><span class="sxs-lookup"><span data-stu-id="46d41-102">IMetaDataTables::GetNextUserString Method</span></span>

<span data-ttu-id="46d41-103">현재 테이블 열에 하드 코딩 된 다음 문자열이 포함 된 행의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="46d41-103">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46d41-104">구문</span><span class="sxs-lookup"><span data-stu-id="46d41-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextUserString (  
    [in]  ULONG   ixUserString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46d41-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="46d41-105">Parameters</span></span>  

 `ixUserString`  
 <span data-ttu-id="46d41-106">진행 현재 문자열 열의 인덱스 값입니다.</span><span class="sxs-lookup"><span data-stu-id="46d41-106">[in] An index value from the current string column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="46d41-107">제한이 열에서 다음 문자열의 행 인덱스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="46d41-107">[out] A pointer to the row index of the next string in the column.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46d41-108">설명</span><span class="sxs-lookup"><span data-stu-id="46d41-108">Remarks</span></span>  

 <span data-ttu-id="46d41-109">이 메서드를 사용 하는 것은 일관 된 결과를 반환 하지 않기 때문에 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="46d41-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="46d41-110">GUID 테이블에 대 한 자세한 내용은 CLI (공용 언어 인프라) 설명서, 특히 "Partition II: 메타 데이터 정의 및 의미 체계"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="46d41-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="46d41-111">설명서는 온라인으로 제공 됩니다. [Ecma c # 및 공용 언어 인프라 표준](../../../standard/components.md#applicable-standards) 및 [표준 ECMA-335-CLI (공용 언어 인프라)](http://www.ecma-international.org/publications/standards/Ecma-335.htm)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="46d41-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46d41-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="46d41-112">Requirements</span></span>  

 <span data-ttu-id="46d41-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="46d41-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46d41-114">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="46d41-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="46d41-115">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46d41-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="46d41-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46d41-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46d41-117">참조</span><span class="sxs-lookup"><span data-stu-id="46d41-117">See also</span></span>

- [<span data-ttu-id="46d41-118">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46d41-118">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="46d41-119">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46d41-119">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
