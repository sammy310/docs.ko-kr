---
title: IMetaDataTables::GetNextString 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextString
helpviewer_keywords:
- IMetaDataTables::GetNextString method [.NET Framework metadata]
- GetNextString method [.NET Framework metadata]
ms.assetid: d9720428-c353-4f07-a7e8-899e106a1b37
topic_type:
- apiref
ms.openlocfilehash: 6f4764f016360a2ec0ab054b7a89ccb3f86aeb43
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490226"
---
# <a name="imetadatatablesgetnextstring-method"></a><span data-ttu-id="ba8de-102">IMetaDataTables::GetNextString 메서드</span><span class="sxs-lookup"><span data-stu-id="ba8de-102">IMetaDataTables::GetNextString Method</span></span>
<span data-ttu-id="ba8de-103">현재 테이블 열에서 다음 문자열의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ba8de-103">Gets the index of the next string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ba8de-104">구문</span><span class="sxs-lookup"><span data-stu-id="ba8de-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextString (
    [in]  ULONG   ixString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ba8de-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ba8de-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="ba8de-106">진행 문자열 테이블 열의 인덱스 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ba8de-106">[in] The index value from a string table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="ba8de-107">제한이 열에서 다음 문자열의 인덱스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ba8de-107">[out] A pointer to the index of the next string in the column.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ba8de-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ba8de-108">Requirements</span></span>  
 <span data-ttu-id="ba8de-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ba8de-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ba8de-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="ba8de-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ba8de-111">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba8de-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ba8de-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ba8de-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba8de-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ba8de-113">See also</span></span>

- [<span data-ttu-id="ba8de-114">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ba8de-114">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="ba8de-115">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ba8de-115">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
