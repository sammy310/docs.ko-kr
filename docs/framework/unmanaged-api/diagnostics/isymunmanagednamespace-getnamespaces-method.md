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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3d7ac84971f7d0e97f7ccd26710151d1aeefe729
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939505"
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a><span data-ttu-id="08b62-102">ISymUnmanagedNamespace::GetNamespaces 메서드</span><span class="sxs-lookup"><span data-stu-id="08b62-102">ISymUnmanagedNamespace::GetNamespaces Method</span></span>
<span data-ttu-id="08b62-103">이 네임 스페이스의 자식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="08b62-103">Gets the children of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08b62-104">구문</span><span class="sxs-lookup"><span data-stu-id="08b62-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08b62-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="08b62-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="08b62-106">[in] A `ULONG32` 의 크기를 나타내는 `namespaces` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="08b62-106">[in] A `ULONG32` that indicates the size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="08b62-107">[out] 에 대 한 포인터를 `ULONG32` 문자 네임 스페이스를 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="08b62-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="08b62-108">[out] 네임 스페이스를 포함 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="08b62-108">[out] A pointer to the buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08b62-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="08b62-109">Return Value</span></span>  
 <span data-ttu-id="08b62-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="08b62-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08b62-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="08b62-111">Requirements</span></span>  
 <span data-ttu-id="08b62-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="08b62-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08b62-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="08b62-113">See also</span></span>

- [<span data-ttu-id="08b62-114">ISymUnmanagedNamespace 인터페이스</span><span class="sxs-lookup"><span data-stu-id="08b62-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
