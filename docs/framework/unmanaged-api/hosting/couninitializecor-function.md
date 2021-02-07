---
description: '자세히 알아보기: CoUninitializeCor 함수'
title: CoUninitializeCor 함수
ms.date: 03/30/2017
api_name:
- CoUninitializeCor
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeCor
helpviewer_keywords:
- CoUninitializeCor function [.NET Framework hosting]
ms.assetid: 50a95b8b-9766-470e-bb29-2c7ecddfd4a1
topic_type:
- apiref
ms.openlocfilehash: 1aa3482b6891779b4c85c29079ccd26d7170934e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746206"
---
# <a name="couninitializecor-function"></a><span data-ttu-id="e8190-103">CoUninitializeCor 함수</span><span class="sxs-lookup"><span data-stu-id="e8190-103">CoUninitializeCor Function</span></span>

<span data-ttu-id="e8190-104">`CoUninitializeCor`는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8190-104">`CoUninitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8190-105">구문</span><span class="sxs-lookup"><span data-stu-id="e8190-105">Syntax</span></span>  
  
```cpp  
STDAPI_(void) CoUninitializeCor(void);  
```  
  
## <a name="remarks"></a><span data-ttu-id="e8190-106">설명</span><span class="sxs-lookup"><span data-stu-id="e8190-106">Remarks</span></span>  

 <span data-ttu-id="e8190-107">프로세스에서 공용 언어 런타임을 언로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e8190-107">The common language runtime cannot be unloaded from a process.</span></span> <span data-ttu-id="e8190-108">실행 중인 프로세스에서 런타임을 완전히 제거 하려면 해당 프로세스를 종료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8190-108">To completely remove the runtime from a running process, you must shut down that process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8190-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e8190-109">See also</span></span>

- [<span data-ttu-id="e8190-110">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="e8190-110">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
