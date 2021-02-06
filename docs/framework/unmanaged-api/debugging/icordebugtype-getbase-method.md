---
description: '자세히 알아보기: ICorDebugType:: GetBase 메서드'
title: ICorDebugType::GetBase 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetBase
helpviewer_keywords:
- ICorDebugType::GetBase method [.NET Framework debugging]
- GetBase method [.NET Framework debugging]
ms.assetid: f24e1af9-c220-4f79-ae62-4153ec17ea81
topic_type:
- apiref
ms.openlocfilehash: 78cd540974b540b704e946f6c723214d72e89ab4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658388"
---
# <a name="icordebugtypegetbase-method"></a><span data-ttu-id="3b264-103">ICorDebugType::GetBase 메서드</span><span class="sxs-lookup"><span data-stu-id="3b264-103">ICorDebugType::GetBase Method</span></span>

<span data-ttu-id="3b264-104">이가 나타내는 형식의 기본 형식 (있는 경우)을 나타내는 ICorDebugType에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="3b264-104">Gets an interface pointer to an ICorDebugType that represents the base type, if one exists, of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b264-105">구문</span><span class="sxs-lookup"><span data-stu-id="3b264-105">Syntax</span></span>  
  
```cpp  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b264-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3b264-106">Parameters</span></span>  

 `pBase`  
 <span data-ttu-id="3b264-107">제한이 기본 형식을 나타내는 개체의 주소에 대 한 포인터입니다 `ICorDebugType` .</span><span class="sxs-lookup"><span data-stu-id="3b264-107">[out] A pointer to the address of an `ICorDebugType` object that represents the base type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b264-108">설명</span><span class="sxs-lookup"><span data-stu-id="3b264-108">Remarks</span></span>  

 <span data-ttu-id="3b264-109">형식에 대 한 기본 형식을 조회 하는 것은 개체 또는 해당 부모 클래스의 모든 필드를 인쇄 하는 등의 일반적인 디버거 기능을 구현 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b264-109">Looking up the base type for a type is useful to implement common debugger functionality, such as printing out all the fields of an object or its parent classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b264-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3b264-110">Requirements</span></span>  

 <span data-ttu-id="3b264-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3b264-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b264-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3b264-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3b264-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b264-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b264-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b264-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
