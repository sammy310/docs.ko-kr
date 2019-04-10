---
title: ISymUnmanagedReader::GetUserEntryPoint 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetUserEntryPoint
helpviewer_keywords:
- GetUserEntryPoint method [.NET Framework debugging]
- ISymUnmanagedReader::GetUserEntryPoint method [.NET Framework debugging]
ms.assetid: 3fd3a34c-d176-46e9-9996-fb1646cff9b0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0267ae8b57c837b097d496c8e119085d03417e36
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211272"
---
# <a name="isymunmanagedreadergetuserentrypoint-method"></a><span data-ttu-id="97804-102">ISymUnmanagedReader::GetUserEntryPoint 메서드</span><span class="sxs-lookup"><span data-stu-id="97804-102">ISymUnmanagedReader::GetUserEntryPoint Method</span></span>
<span data-ttu-id="97804-103">있는 경우 모듈의 사용자 진입점으로 지정 된 메서드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="97804-103">Returns the method that was specified as the user entry point for the module, if any.</span></span> <span data-ttu-id="97804-104">예를 들어이 메서드는 main 메서드의 전에 컴파일러에서 생성 된 스텁이 아닌 사용자의 기본 메서드 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97804-104">For example, this method could be the user's main method rather than compiler-generated stubs before the main method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97804-105">구문</span><span class="sxs-lookup"><span data-stu-id="97804-105">Syntax</span></span>  
  
```  
HRESULT GetUserEntryPoint (  
    [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97804-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="97804-106">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="97804-107">[out] 진입점을 수신 하는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="97804-107">[out] A pointer to a variable that receives the entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="97804-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="97804-108">Return Value</span></span>  
 <span data-ttu-id="97804-109">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="97804-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97804-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="97804-110">Requirements</span></span>  
 <span data-ttu-id="97804-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="97804-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97804-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="97804-112">See also</span></span>

- [<span data-ttu-id="97804-113">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="97804-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
