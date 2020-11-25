---
title: ISymUnmanagedNamespace::GetNamespaces 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedNamespace.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedNamespace::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedNamespace::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 0ea9d9af-8709-4a46-872b-f54d9e840088
topic_type:
- apiref
ms.openlocfilehash: 8eef973c4c054b704b7c3f798e5dc1aa455dda96
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707777"
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a><span data-ttu-id="2c203-102">ISymUnmanagedNamespace::GetNamespaces 메서드</span><span class="sxs-lookup"><span data-stu-id="2c203-102">ISymUnmanagedNamespace::GetNamespaces Method</span></span>

<span data-ttu-id="2c203-103">이 네임 스페이스의 자식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2c203-103">Gets the children of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c203-104">구문</span><span class="sxs-lookup"><span data-stu-id="2c203-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c203-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2c203-105">Parameters</span></span>  

 `cNameSpaces`  
 <span data-ttu-id="2c203-106">진행 `ULONG32` 배열의 크기를 나타내는입니다 `namespaces` .</span><span class="sxs-lookup"><span data-stu-id="2c203-106">[in] A `ULONG32` that indicates the size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="2c203-107">제한이 `ULONG32` 네임 스페이스를 포함 하는 데 필요한 버퍼의 크기 (문자 수)를 받는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2c203-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="2c203-108">제한이 네임 스페이스를 포함 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2c203-108">[out] A pointer to the buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c203-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="2c203-109">Return Value</span></span>  

 <span data-ttu-id="2c203-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="2c203-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c203-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2c203-111">Requirements</span></span>  

 <span data-ttu-id="2c203-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="2c203-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c203-113">참조</span><span class="sxs-lookup"><span data-stu-id="2c203-113">See also</span></span>

- [<span data-ttu-id="2c203-114">ISymUnmanagedNamespace 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2c203-114">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)
