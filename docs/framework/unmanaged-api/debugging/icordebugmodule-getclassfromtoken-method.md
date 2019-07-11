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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e6da6fabc6632bea58b28a00f55d05f4c2cc5b46
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67762681"
---
# <a name="icordebugmodulegetclassfromtoken-method"></a><span data-ttu-id="eafc5-102">ICorDebugModule::GetClassFromToken 메서드</span><span class="sxs-lookup"><span data-stu-id="eafc5-102">ICorDebugModule::GetClassFromToken Method</span></span>
<span data-ttu-id="eafc5-103">메타 데이터 토큰이 지정 된 클래스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="eafc5-103">Gets the class specified by the metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eafc5-104">구문</span><span class="sxs-lookup"><span data-stu-id="eafc5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetClassFromToken(  
    [in]  mdTypeDef        typeDef,  
    [out] ICorDebugClass **ppClass  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eafc5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="eafc5-105">Parameters</span></span>  
 `typedef`  
 <span data-ttu-id="eafc5-106">[in] `mdTypeDef` 클래스의 메타 데이터를 참조 하는 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="eafc5-106">[in] An `mdTypeDef` metadata token that references the metadata of a class.</span></span>  
  
 `ppClass`  
 <span data-ttu-id="eafc5-107">[out] 클래스를 나타내는 ICorDebugClass 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="eafc5-107">[out] A pointer to the address of an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eafc5-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eafc5-108">Requirements</span></span>  
 <span data-ttu-id="eafc5-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="eafc5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eafc5-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eafc5-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eafc5-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eafc5-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eafc5-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eafc5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
