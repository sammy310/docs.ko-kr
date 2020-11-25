---
title: IMetaDataEmit2::SaveDelta 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDelta
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDelta
helpviewer_keywords:
- IMetaDataEmit2::SaveDelta method [.NET Framework metadata]
- SaveDelta method [.NET Framework metadata]
ms.assetid: b95739fe-d2fa-4776-ae0d-31d9707ef799
topic_type:
- apiref
ms.openlocfilehash: ab2f30c485a755d4788926c13c2608e55a716c5c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704268"
---
# <a name="imetadataemit2savedelta-method"></a><span data-ttu-id="d18db-102">IMetaDataEmit2::SaveDelta 메서드</span><span class="sxs-lookup"><span data-stu-id="d18db-102">IMetaDataEmit2::SaveDelta Method</span></span>

<span data-ttu-id="d18db-103">현재 편집 하며 계속 하기 세션의 변경 내용을 지정 된 파일에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d18db-103">Saves changes from the current edit-and-continue session to the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d18db-104">구문</span><span class="sxs-lookup"><span data-stu-id="d18db-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDelta (  
    [in] LPCWSTR     szFile,
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d18db-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d18db-105">Parameters</span></span>  

 `szFile`  
 <span data-ttu-id="d18db-106">진행 변경 내용을 저장할 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d18db-106">[in] The file name under which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="d18db-107">[in] 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d18db-107">[in] Reserved.</span></span> <span data-ttu-id="d18db-108">0이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d18db-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d18db-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d18db-109">Requirements</span></span>  

 <span data-ttu-id="d18db-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d18db-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d18db-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="d18db-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d18db-112">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d18db-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d18db-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d18db-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d18db-114">참조</span><span class="sxs-lookup"><span data-stu-id="d18db-114">See also</span></span>

- [<span data-ttu-id="d18db-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d18db-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="d18db-116">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d18db-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
