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
ms.openlocfilehash: a1cd932051a9ed90a29ff5eeaa818a67104192bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175254"
---
# <a name="imetadatatablesgetnextstring-method"></a><span data-ttu-id="5bf36-102">IMetaDataTables::GetNextString 메서드</span><span class="sxs-lookup"><span data-stu-id="5bf36-102">IMetaDataTables::GetNextString Method</span></span>
<span data-ttu-id="5bf36-103">현재 테이블 열에서 다음 문자열의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5bf36-103">Gets the index of the next string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bf36-104">구문</span><span class="sxs-lookup"><span data-stu-id="5bf36-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextString (
    [in]  ULONG   ixString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5bf36-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5bf36-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="5bf36-106">【인】 문자열 테이블 열의 인덱스 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5bf36-106">[in] The index value from a string table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="5bf36-107">【아웃】 열의 다음 문자열 인덱스에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5bf36-107">[out] A pointer to the index of the next string in the column.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bf36-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5bf36-108">Requirements</span></span>  
 <span data-ttu-id="5bf36-109">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5bf36-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bf36-110">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="5bf36-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5bf36-111">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="5bf36-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5bf36-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bf36-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bf36-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5bf36-113">See also</span></span>

- [<span data-ttu-id="5bf36-114">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5bf36-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="5bf36-115">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5bf36-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
