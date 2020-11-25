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
ms.openlocfilehash: f0a688aef9fbc6f7bfac85e06cbe7e76704d3230
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720533"
---
# <a name="isymunmanagedreadergetuserentrypoint-method"></a><span data-ttu-id="4b9f6-102">ISymUnmanagedReader::GetUserEntryPoint 메서드</span><span class="sxs-lookup"><span data-stu-id="4b9f6-102">ISymUnmanagedReader::GetUserEntryPoint Method</span></span>

<span data-ttu-id="4b9f6-103">모듈에 대 한 사용자 진입점으로 지정 된 메서드를 반환 합니다 (있는 경우).</span><span class="sxs-lookup"><span data-stu-id="4b9f6-103">Returns the method that was specified as the user entry point for the module, if any.</span></span> <span data-ttu-id="4b9f6-104">예를 들어이 메서드는 main 메서드 이전의 컴파일러 생성 스텁이 아닌 사용자의 main 메서드 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b9f6-104">For example, this method could be the user's main method rather than compiler-generated stubs before the main method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b9f6-105">구문</span><span class="sxs-lookup"><span data-stu-id="4b9f6-105">Syntax</span></span>  
  
```cpp  
HRESULT GetUserEntryPoint (  
    [out, retval]  mdMethodDef  *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b9f6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4b9f6-106">Parameters</span></span>  

 `pToken`  
 <span data-ttu-id="4b9f6-107">제한이 진입점을 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4b9f6-107">[out] A pointer to a variable that receives the entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4b9f6-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="4b9f6-108">Return Value</span></span>  

 <span data-ttu-id="4b9f6-109">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="4b9f6-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b9f6-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4b9f6-110">Requirements</span></span>  

 <span data-ttu-id="4b9f6-111">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="4b9f6-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b9f6-112">참조</span><span class="sxs-lookup"><span data-stu-id="4b9f6-112">See also</span></span>

- [<span data-ttu-id="4b9f6-113">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4b9f6-113">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
