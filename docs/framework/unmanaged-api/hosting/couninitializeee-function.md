---
title: CoUninitializeEE 함수
ms.date: 03/30/2017
api_name:
- CoUninitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeEE
helpviewer_keywords:
- CoUninitializeEE function [.NET Framework hosting]
ms.assetid: 5f5a311a-839a-465f-89d9-ff1c74da9736
topic_type:
- apiref
ms.openlocfilehash: fa6297e926d53c02bb0d1af7b59b45b8ee152399
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616465"
---
# <a name="couninitializeee-function"></a><span data-ttu-id="8d9d4-102">CoUninitializeEE 함수</span><span class="sxs-lookup"><span data-stu-id="8d9d4-102">CoUninitializeEE Function</span></span>
<span data-ttu-id="8d9d4-103">`CoUninitializeEE`는 사용 되지 않으며 기능을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d9d4-103">`CoUninitializeEE` is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d9d4-104">구문</span><span class="sxs-lookup"><span data-stu-id="8d9d4-104">Syntax</span></span>  
  
```cpp  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="8d9d4-105">설명</span><span class="sxs-lookup"><span data-stu-id="8d9d4-105">Remarks</span></span>  
 <span data-ttu-id="8d9d4-106">프로세스에서 공용 언어 런타임 실행 엔진을 언로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8d9d4-106">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="8d9d4-107">실행 엔진을 종료 하려면 [Corexitprocess](corexitprocess-function.md)를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9d4-107">To shut down the execution engine call [CorExitProcess](corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d9d4-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8d9d4-108">See also</span></span>

- [<span data-ttu-id="8d9d4-109">CoInitializeEE 함수</span><span class="sxs-lookup"><span data-stu-id="8d9d4-109">CoInitializeEE Function</span></span>](coinitializeee-function.md)
- [<span data-ttu-id="8d9d4-110">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="8d9d4-110">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
