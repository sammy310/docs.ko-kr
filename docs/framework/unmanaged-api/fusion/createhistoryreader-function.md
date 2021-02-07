---
description: '자세히 알아보기: CreateHistoryReader 함수'
title: CreateHistoryReader 함수
ms.date: 03/30/2017
api_name:
- CreateHistoryReader
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateHistoryReader
helpviewer_keywords:
- CreateHistoryReader function [.NET Framework fusion]
ms.assetid: 66a89acf-8c32-44c0-8787-960c99c7b3ec
topic_type:
- apiref
ms.openlocfilehash: 0943f3d0f3322d34ed92c0a96b909e4d63ec5e7f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761124"
---
# <a name="createhistoryreader-function"></a><span data-ttu-id="ceb3a-103">CreateHistoryReader 함수</span><span class="sxs-lookup"><span data-stu-id="ceb3a-103">CreateHistoryReader Function</span></span>

<span data-ttu-id="ceb3a-104">지정 된 파일에 대 한 기록 판독기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ceb3a-104">Creates a history reader for the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ceb3a-105">구문</span><span class="sxs-lookup"><span data-stu-id="ceb3a-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="ceb3a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ceb3a-106">Parameters</span></span>  

 `wzFilePath`  
 <span data-ttu-id="ceb3a-107">진행 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="ceb3a-107">[in] The file path.</span></span>  
  
 `ppHistoryReader`  
 <span data-ttu-id="ceb3a-108">제한이 성공적으로 완료 되 면 기록 판독기에 대 한 포인터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb3a-108">[out] On successful completion, contains a pointer to the history reader.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ceb3a-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="ceb3a-109">Return Value</span></span>  

 <span data-ttu-id="ceb3a-110">이 메서드는 Winerror.h에 정의 된 대로 표준 COM 오류 코드와 함께 다음 표에 설명 된 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb3a-110">This method returns standard COM error codes as defined in WinError.h, in addition to the values described in the following table.</span></span>  
  
|<span data-ttu-id="ceb3a-111">반환 코드</span><span class="sxs-lookup"><span data-stu-id="ceb3a-111">Return code</span></span>|<span data-ttu-id="ceb3a-112">설명</span><span class="sxs-lookup"><span data-stu-id="ceb3a-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="ceb3a-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="ceb3a-113">S_OK</span></span>|<span data-ttu-id="ceb3a-114">메서드가 성공적으로 완료 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ceb3a-114">Indicates that the method completed successfully.</span></span>|  
|<span data-ttu-id="ceb3a-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ceb3a-115">E_INVALIDARG</span></span>|<span data-ttu-id="ceb3a-116">`wzFilePath`또는 `ppHistoryReader` 가 null 참조로 설정 됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ceb3a-116">Indicates that `wzFilePath` or `ppHistoryReader` are set to a null reference.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ceb3a-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ceb3a-117">Requirements</span></span>  

 <span data-ttu-id="ceb3a-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ceb3a-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ceb3a-119">**라이브러리:** Fusion.dll</span><span class="sxs-lookup"><span data-stu-id="ceb3a-119">**Library:** Fusion.dll</span></span>  
  
 <span data-ttu-id="ceb3a-120">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ceb3a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceb3a-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ceb3a-121">See also</span></span>

- [<span data-ttu-id="ceb3a-122">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="ceb3a-122">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
