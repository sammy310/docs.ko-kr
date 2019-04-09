---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e438006d6424866514e73119c05e8fd69d7ba62e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132264"
---
# <a name="createhistoryreader-function"></a><span data-ttu-id="b751a-102">CreateHistoryReader 함수</span><span class="sxs-lookup"><span data-stu-id="b751a-102">CreateHistoryReader Function</span></span>
<span data-ttu-id="b751a-103">지정된 된 파일에 대 한 기록 판독기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b751a-103">Creates a history reader for the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b751a-104">구문</span><span class="sxs-lookup"><span data-stu-id="b751a-104">Syntax</span></span>  
  
```  
HRESULT CreateHistoryReader (  
    [in]  LPCWSTR        wzFilePath,  
    [out] IHistoryReader **ppHistoryReader  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="b751a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b751a-105">Parameters</span></span>  
 `wzFilePath`  
 <span data-ttu-id="b751a-106">[in] 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="b751a-106">[in] The file path.</span></span>  
  
 `ppHistoryReader`  
 <span data-ttu-id="b751a-107">[out] 성공적으로 완료 되 면 기록 판독기에 대 한 포인터를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b751a-107">[out] On successful completion, contains a pointer to the history reader.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b751a-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="b751a-108">Return Value</span></span>  
 <span data-ttu-id="b751a-109">이 메서드는 다음 표에 설명 된 값 외에도 WinError.h에 정의 된 대로 표준 COM 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b751a-109">This method returns standard COM error codes as defined in WinError.h, in addition to the values described in the following table.</span></span>  
  
|<span data-ttu-id="b751a-110">반환 코드</span><span class="sxs-lookup"><span data-stu-id="b751a-110">Return code</span></span>|<span data-ttu-id="b751a-111">설명</span><span class="sxs-lookup"><span data-stu-id="b751a-111">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="b751a-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="b751a-112">S_OK</span></span>|<span data-ttu-id="b751a-113">메서드가 성공적으로 완료 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b751a-113">Indicates that the method completed successfully.</span></span>|  
|<span data-ttu-id="b751a-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="b751a-114">E_INVALIDARG</span></span>|<span data-ttu-id="b751a-115">함을 `wzFilePath` 또는 `ppHistoryReader` null 참조로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b751a-115">Indicates that `wzFilePath` or `ppHistoryReader` are set to a null reference.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b751a-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b751a-116">Requirements</span></span>  
 <span data-ttu-id="b751a-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b751a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b751a-118">**라이브러리:** Fusion.dll</span><span class="sxs-lookup"><span data-stu-id="b751a-118">**Library:** Fusion.dll</span></span>  
  
 **<span data-ttu-id="b751a-119">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="b751a-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b751a-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="b751a-120">See also</span></span>

- [<span data-ttu-id="b751a-121">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="b751a-121">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
