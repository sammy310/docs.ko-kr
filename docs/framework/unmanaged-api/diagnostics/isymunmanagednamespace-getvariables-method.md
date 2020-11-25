---
title: ISymUnmanagedNamespace::GetVariables 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetVariables
helpviewer_keywords:
- ISymUnmanagedNamespace::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: ea7c1617-f3ce-4220-8288-f2b50eaf0f0f
topic_type:
- apiref
ms.openlocfilehash: f554fa95f552285ad92d9f780a8d77f53e6890b6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707700"
---
# <a name="isymunmanagednamespacegetvariables-method"></a><span data-ttu-id="87c93-102">ISymUnmanagedNamespace::GetVariables 메서드</span><span class="sxs-lookup"><span data-stu-id="87c93-102">ISymUnmanagedNamespace::GetVariables Method</span></span>

<span data-ttu-id="87c93-103">이 네임 스페이스의 전역 범위에 정의 된 모든 변수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="87c93-103">Returns all variables defined at global scope within this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87c93-104">구문</span><span class="sxs-lookup"><span data-stu-id="87c93-104">Syntax</span></span>  
  
```cpp
HRESULT GetVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars), length_is(*pcVars)]  
        ISymUnmanagedVariable *pVars[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87c93-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="87c93-105">Parameters</span></span>  

 `cVars`  
 <span data-ttu-id="87c93-106">진행 `ULONG32` 배열의 크기를 나타내는입니다 `pVars` .</span><span class="sxs-lookup"><span data-stu-id="87c93-106">[in] A `ULONG32` that indicates the size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="87c93-107">제한이 `ULONG32` 네임 스페이스를 포함 하는 데 필요한 버퍼의 크기를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="87c93-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `pVars`  
 <span data-ttu-id="87c93-108">제한이 네임 스페이스를 포함 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="87c93-108">[out] A pointer to a buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87c93-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="87c93-109">Return Value</span></span>  

 <span data-ttu-id="87c93-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="87c93-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87c93-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="87c93-111">Requirements</span></span>  

 <span data-ttu-id="87c93-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="87c93-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87c93-113">참조</span><span class="sxs-lookup"><span data-stu-id="87c93-113">See also</span></span>

- [<span data-ttu-id="87c93-114">ISymUnmanagedNamespace 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87c93-114">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)
