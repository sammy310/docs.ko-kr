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
ms.openlocfilehash: 8ecaa003084064be1071a85aa726c38d773ec0b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672580"
---
# <a name="imetadatatablesgetstring-method"></a><span data-ttu-id="df4d1-102">IMetaDataTables::GetString 메서드</span><span class="sxs-lookup"><span data-stu-id="df4d1-102">IMetaDataTables::GetString Method</span></span>

<span data-ttu-id="df4d1-103">현재 참조 범위의 테이블 열에서 지정 된 인덱스에 있는 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="df4d1-103">Gets the string at the specified index from the table column in the current reference scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df4d1-104">구문</span><span class="sxs-lookup"><span data-stu-id="df4d1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetString (
    [in]  ULONG       ixString,  
    [out] const char  **ppString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df4d1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="df4d1-105">Parameters</span></span>  

 `ixString`  
 <span data-ttu-id="df4d1-106">진행 다음 값을 검색 하기 시작할 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="df4d1-106">[in] The index at which to start to search for the next value.</span></span>  
  
 `ppString`  
 <span data-ttu-id="df4d1-107">제한이 반환 된 문자열 값에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="df4d1-107">[out] A pointer to a pointer to the returned string value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df4d1-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="df4d1-108">Requirements</span></span>  

 <span data-ttu-id="df4d1-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="df4d1-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df4d1-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="df4d1-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="df4d1-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df4d1-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="df4d1-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df4d1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df4d1-113">참조</span><span class="sxs-lookup"><span data-stu-id="df4d1-113">See also</span></span>

- [<span data-ttu-id="df4d1-114">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="df4d1-114">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="df4d1-115">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="df4d1-115">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
