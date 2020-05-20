---
title: ISymUnmanagedReader::GetNamespaces 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetNamespaces
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedReader::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 3feb4796-2fab-45ce-beca-6f5bc530b971
topic_type:
- apiref
ms.openlocfilehash: 44f9284f0a89f0941940cf379c48b2b138149122
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614944"
---
# <a name="isymunmanagedreadergetnamespaces-method"></a><span data-ttu-id="d7647-102">ISymUnmanagedReader::GetNamespaces 메서드</span><span class="sxs-lookup"><span data-stu-id="d7647-102">ISymUnmanagedReader::GetNamespaces Method</span></span>
<span data-ttu-id="d7647-103">이 기호 저장소의 전역 범위에서 정의 된 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d7647-103">Gets the namespaces defined at global scope within this symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7647-104">구문</span><span class="sxs-lookup"><span data-stu-id="d7647-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces (  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is (cNameSpaces),  
        length_is (*pcNameSpaces)]  
        ISymUnmanagedNamespace*  namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7647-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d7647-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="d7647-106">진행 네임 스페이스 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="d7647-106">[in] The size of the namespaces array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="d7647-107">제한이 네임 스페이스 목록의 길이를 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d7647-107">[out] A pointer to a variable that receives the length of the namespace list.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="d7647-108">제한이 네임 스페이스 목록을 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d7647-108">[out] A pointer to a variable that receives the namespace list.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d7647-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="d7647-109">Return Value</span></span>  
 <span data-ttu-id="d7647-110">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="d7647-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7647-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d7647-111">Requirements</span></span>  
 <span data-ttu-id="d7647-112">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="d7647-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7647-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7647-113">See also</span></span>

- [<span data-ttu-id="d7647-114">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d7647-114">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
