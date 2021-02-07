---
description: '자세히 알아보기: ICorDebugModule:: GetClassFromToken 메서드'
title: ICorDebugModule::GetClassFromToken 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetClassFromToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetClassFromToken
helpviewer_keywords:
- GetClassFromToken method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetClassFromToken method [.NET Framework debugging]
ms.assetid: 622a4d3c-0425-4c54-a7e4-0735377cdad2
topic_type:
- apiref
ms.openlocfilehash: 8184c6c1920a4397c4037160276b5b86033baf71
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722617"
---
# <a name="icordebugmodulegetclassfromtoken-method"></a><span data-ttu-id="38dfd-103">ICorDebugModule::GetClassFromToken 메서드</span><span class="sxs-lookup"><span data-stu-id="38dfd-103">ICorDebugModule::GetClassFromToken Method</span></span>

<span data-ttu-id="38dfd-104">메타 데이터 토큰에 의해 지정 된 클래스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="38dfd-104">Gets the class specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38dfd-105">구문</span><span class="sxs-lookup"><span data-stu-id="38dfd-105">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  mdTypeDef        typeDef,  
    [out] ICorDebugClass **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38dfd-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="38dfd-106">Parameters</span></span>  

 `typedef`  
 <span data-ttu-id="38dfd-107">진행 `mdTypeDef` 클래스의 메타 데이터를 참조 하는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="38dfd-107">[in] An `mdTypeDef` metadata token that references the metadata of a class.</span></span>  
  
 `ppClass`  
 <span data-ttu-id="38dfd-108">제한이 클래스를 나타내는 ICorDebugClass 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="38dfd-108">[out] A pointer to the address of an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38dfd-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="38dfd-109">Requirements</span></span>  

 <span data-ttu-id="38dfd-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="38dfd-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38dfd-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="38dfd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38dfd-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38dfd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38dfd-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38dfd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
