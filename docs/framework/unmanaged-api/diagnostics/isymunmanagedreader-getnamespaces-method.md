---
description: '자세히 알아보기: ISymUnmanagedReader:: GetNamespaces 스페이스 메서드'
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
ms.openlocfilehash: 47f7bff829ca2a52eb95d7d7693a7486301de092
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764010"
---
# <a name="isymunmanagedreadergetnamespaces-method"></a><span data-ttu-id="6e72c-103">ISymUnmanagedReader::GetNamespaces 메서드</span><span class="sxs-lookup"><span data-stu-id="6e72c-103">ISymUnmanagedReader::GetNamespaces Method</span></span>

<span data-ttu-id="6e72c-104">이 기호 저장소의 전역 범위에서 정의 된 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6e72c-104">Gets the namespaces defined at global scope within this symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e72c-105">구문</span><span class="sxs-lookup"><span data-stu-id="6e72c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNamespaces (  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is (cNameSpaces),  
        length_is (*pcNameSpaces)]  
        ISymUnmanagedNamespace*  namespaces[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6e72c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6e72c-106">Parameters</span></span>  

 `cNameSpaces`  
 <span data-ttu-id="6e72c-107">진행 네임 스페이스 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="6e72c-107">[in] The size of the namespaces array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="6e72c-108">제한이 네임 스페이스 목록의 길이를 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6e72c-108">[out] A pointer to a variable that receives the length of the namespace list.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="6e72c-109">제한이 네임 스페이스 목록을 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6e72c-109">[out] A pointer to a variable that receives the namespace list.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6e72c-110">Return Value</span><span class="sxs-lookup"><span data-stu-id="6e72c-110">Return Value</span></span>  

 <span data-ttu-id="6e72c-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="6e72c-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e72c-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6e72c-112">Requirements</span></span>  

 <span data-ttu-id="6e72c-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="6e72c-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e72c-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e72c-114">See also</span></span>

- [<span data-ttu-id="6e72c-115">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6e72c-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
