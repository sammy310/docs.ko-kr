---
description: '자세히 알아보기: ICLRTaskManager:: GetCurrentTaskType 메서드'
title: ICLRTaskManager::GetCurrentTaskType 메서드
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.GetCurrentTaskType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTaskType
helpviewer_keywords:
- GetCurrentTaskType method [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTaskType method [.NET Framework hosting]
ms.assetid: 6b0d9259-dbe2-45bb-b34d-990f60c73424
topic_type:
- apiref
ms.openlocfilehash: 984cc490123d6146737d3f018fdf712c7c528635
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799488"
---
# <a name="iclrtaskmanagergetcurrenttasktype-method"></a><span data-ttu-id="99e92-103">ICLRTaskManager::GetCurrentTaskType 메서드</span><span class="sxs-lookup"><span data-stu-id="99e92-103">ICLRTaskManager::GetCurrentTaskType Method</span></span>

<span data-ttu-id="99e92-104">현재 실행 중인 작업의 형식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="99e92-104">Gets the type of the task that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99e92-105">구문</span><span class="sxs-lookup"><span data-stu-id="99e92-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTaskType(  
    [out] ETaskType *pTaskType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="99e92-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="99e92-106">Parameters</span></span>  

 `pTaskType`  
 <span data-ttu-id="99e92-107">제한이 현재 실행 중인 작업의 유형을 나타내는 [Etasktype](etasktype-enumeration.md) 열거형의 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="99e92-107">[out] A pointer to a value of the [ETaskType](etasktype-enumeration.md) enumeration that indicates the type of task that is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99e92-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="99e92-108">Requirements</span></span>  

 <span data-ttu-id="99e92-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="99e92-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99e92-110">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="99e92-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="99e92-111">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99e92-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="99e92-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99e92-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99e92-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99e92-113">See also</span></span>

- [<span data-ttu-id="99e92-114">ICLRTaskManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="99e92-114">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
