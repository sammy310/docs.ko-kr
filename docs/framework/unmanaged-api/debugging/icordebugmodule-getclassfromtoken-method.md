---
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
ms.openlocfilehash: 790999093f874a4d81dd5db74ef012b1d997a12f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73109644"
---
# <a name="icordebugmodulegetclassfromtoken-method"></a><span data-ttu-id="55ac3-102">ICorDebugModule::GetClassFromToken 메서드</span><span class="sxs-lookup"><span data-stu-id="55ac3-102">ICorDebugModule::GetClassFromToken Method</span></span>
<span data-ttu-id="55ac3-103">메타 데이터 토큰에 의해 지정 된 클래스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="55ac3-103">Gets the class specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55ac3-104">구문</span><span class="sxs-lookup"><span data-stu-id="55ac3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  mdTypeDef        typeDef,  
    [out] ICorDebugClass **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55ac3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="55ac3-105">Parameters</span></span>  
 `typedef`  
 <span data-ttu-id="55ac3-106">진행 클래스의 메타 데이터를 참조 하는 `mdTypeDef` 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="55ac3-106">[in] An `mdTypeDef` metadata token that references the metadata of a class.</span></span>  
  
 `ppClass`  
 <span data-ttu-id="55ac3-107">제한이 클래스를 나타내는 ICorDebugClass 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="55ac3-107">[out] A pointer to the address of an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55ac3-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="55ac3-108">Requirements</span></span>  
 <span data-ttu-id="55ac3-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="55ac3-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55ac3-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="55ac3-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55ac3-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55ac3-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55ac3-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55ac3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
