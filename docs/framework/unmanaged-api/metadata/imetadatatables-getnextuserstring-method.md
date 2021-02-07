---
description: '자세히 알아보기: IMetaDataTables:: GetNextUserString 메서드'
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
ms.openlocfilehash: cba1fad18b4f697a5e48ad3b0676bf93f9c66e4e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687963"
---
# <a name="imetadatatablesgetnextuserstring-method"></a><span data-ttu-id="325fd-103">IMetaDataTables::GetNextUserString 메서드</span><span class="sxs-lookup"><span data-stu-id="325fd-103">IMetaDataTables::GetNextUserString Method</span></span>

<span data-ttu-id="325fd-104">현재 테이블 열에 하드 코딩 된 다음 문자열이 포함 된 행의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="325fd-104">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="325fd-105">구문</span><span class="sxs-lookup"><span data-stu-id="325fd-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNextUserString (  
    [in]  ULONG   ixUserString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="325fd-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="325fd-106">Parameters</span></span>  

 `ixUserString`  
 <span data-ttu-id="325fd-107">진행 현재 문자열 열의 인덱스 값입니다.</span><span class="sxs-lookup"><span data-stu-id="325fd-107">[in] An index value from the current string column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="325fd-108">제한이 열에서 다음 문자열의 행 인덱스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="325fd-108">[out] A pointer to the row index of the next string in the column.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="325fd-109">설명</span><span class="sxs-lookup"><span data-stu-id="325fd-109">Remarks</span></span>  

 <span data-ttu-id="325fd-110">이 메서드를 사용 하는 것은 일관 된 결과를 반환 하지 않기 때문에 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="325fd-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="325fd-111">GUID 테이블에 대 한 자세한 내용은 CLI (공용 언어 인프라) 설명서, 특히 "Partition II: 메타 데이터 정의 및 의미 체계"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="325fd-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="325fd-112">설명서는 온라인으로 제공 됩니다. [Ecma c # 및 공용 언어 인프라 표준](../../../standard/components.md#applicable-standards) 및 [표준 ECMA-335-CLI (공용 언어 인프라)](http://www.ecma-international.org/publications/standards/Ecma-335.htm)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="325fd-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="325fd-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="325fd-113">Requirements</span></span>  

 <span data-ttu-id="325fd-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="325fd-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="325fd-115">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="325fd-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="325fd-116">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="325fd-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="325fd-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="325fd-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="325fd-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="325fd-118">See also</span></span>

- [<span data-ttu-id="325fd-119">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="325fd-119">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="325fd-120">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="325fd-120">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
