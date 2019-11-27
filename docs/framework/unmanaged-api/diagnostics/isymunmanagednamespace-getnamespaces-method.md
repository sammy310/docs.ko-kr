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
ms.openlocfilehash: da2906187c02bbc7a35c937663e3fc7db1ebda13
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433892"
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a><span data-ttu-id="294b1-102">ISymUnmanagedNamespace::GetNamespaces 메서드</span><span class="sxs-lookup"><span data-stu-id="294b1-102">ISymUnmanagedNamespace::GetNamespaces Method</span></span>
<span data-ttu-id="294b1-103">이 네임 스페이스의 자식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="294b1-103">Gets the children of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="294b1-104">구문</span><span class="sxs-lookup"><span data-stu-id="294b1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="294b1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="294b1-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="294b1-106">진행 `namespaces` 배열의 크기를 나타내는 `ULONG32`입니다.</span><span class="sxs-lookup"><span data-stu-id="294b1-106">[in] A `ULONG32` that indicates the size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="294b1-107">제한이 네임 스페이스를 포함 하는 데 필요한 버퍼의 크기 (문자 수)를 수신 하는 `ULONG32`에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="294b1-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="294b1-108">제한이 네임 스페이스를 포함 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="294b1-108">[out] A pointer to the buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="294b1-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="294b1-109">Return Value</span></span>  
 <span data-ttu-id="294b1-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="294b1-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="294b1-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="294b1-111">Requirements</span></span>  
 <span data-ttu-id="294b1-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="294b1-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="294b1-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="294b1-113">See also</span></span>

- [<span data-ttu-id="294b1-114">ISymUnmanagedNamespace 인터페이스</span><span class="sxs-lookup"><span data-stu-id="294b1-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
