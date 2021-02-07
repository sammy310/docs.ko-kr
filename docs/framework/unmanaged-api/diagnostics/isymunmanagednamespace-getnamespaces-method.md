---
description: '자세히 알아보기: ISymUnmanagedNamespace:: GetNamespaces 스페이스 메서드'
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
ms.openlocfilehash: f17b16e2a3a7001d16c86dd6dc95241c1b0785e6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709908"
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a><span data-ttu-id="8276c-103">ISymUnmanagedNamespace::GetNamespaces 메서드</span><span class="sxs-lookup"><span data-stu-id="8276c-103">ISymUnmanagedNamespace::GetNamespaces Method</span></span>

<span data-ttu-id="8276c-104">이 네임 스페이스의 자식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8276c-104">Gets the children of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8276c-105">구문</span><span class="sxs-lookup"><span data-stu-id="8276c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8276c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8276c-106">Parameters</span></span>  

 `cNameSpaces`  
 <span data-ttu-id="8276c-107">진행 `ULONG32` 배열의 크기를 나타내는입니다 `namespaces` .</span><span class="sxs-lookup"><span data-stu-id="8276c-107">[in] A `ULONG32` that indicates the size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="8276c-108">제한이 `ULONG32` 네임 스페이스를 포함 하는 데 필요한 버퍼의 크기 (문자 수)를 받는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8276c-108">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="8276c-109">제한이 네임 스페이스를 포함 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8276c-109">[out] A pointer to the buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8276c-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="8276c-110">Return Value</span></span>  

 <span data-ttu-id="8276c-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="8276c-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8276c-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8276c-112">Requirements</span></span>  

 <span data-ttu-id="8276c-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="8276c-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8276c-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8276c-114">See also</span></span>

- [<span data-ttu-id="8276c-115">ISymUnmanagedNamespace 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8276c-115">ISymUnmanagedNamespace Interface</span></span>](isymunmanagednamespace-interface.md)
