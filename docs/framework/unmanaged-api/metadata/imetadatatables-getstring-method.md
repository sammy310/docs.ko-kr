---
title: IMetaDataTables::GetString 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetString
helpviewer_keywords:
- IMetaDataTables::GetString method [.NET Framework metadata]
- GetString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 895c35cf-b95d-4e3b-93b5-cfc1cf9044fc
topic_type:
- apiref
ms.openlocfilehash: 216a1f7bd2ff5a596fa7abf7874b5e603d5a9f7b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175241"
---
# <a name="imetadatatablesgetstring-method"></a><span data-ttu-id="2a39f-102">IMetaDataTables::GetString 메서드</span><span class="sxs-lookup"><span data-stu-id="2a39f-102">IMetaDataTables::GetString Method</span></span>
<span data-ttu-id="2a39f-103">현재 참조 범위의 테이블 열에서 지정된 인덱스에 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2a39f-103">Gets the string at the specified index from the table column in the current reference scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a39f-104">구문</span><span class="sxs-lookup"><span data-stu-id="2a39f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetString (
    [in]  ULONG       ixString,  
    [out] const char  **ppString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a39f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2a39f-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="2a39f-106">【인】 다음 값을 검색하기 시작할 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="2a39f-106">[in] The index at which to start to search for the next value.</span></span>  
  
 `ppString`  
 <span data-ttu-id="2a39f-107">【아웃】 반환 된 문자열 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2a39f-107">[out] A pointer to a pointer to the returned string value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a39f-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2a39f-108">Requirements</span></span>  
 <span data-ttu-id="2a39f-109">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2a39f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a39f-110">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="2a39f-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2a39f-111">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="2a39f-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2a39f-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a39f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a39f-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2a39f-113">See also</span></span>

- [<span data-ttu-id="2a39f-114">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a39f-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="2a39f-115">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a39f-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
