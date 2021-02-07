---
description: '자세히 알아보기: ISymUnmanagedReader:: GetMethodFromDocumentPosition 메서드'
title: ISymUnmanagedReader::GetMethodFromDocumentPosition 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodFromDocumentPosition
helpviewer_keywords:
- GetMethodFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 55773dbc-9053-46e3-8a3c-86caa9d91fb4
topic_type:
- apiref
ms.openlocfilehash: 1289b02f8ea8440dcd1b308b6c91a46a213cabb2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99764088"
---
# <a name="isymunmanagedreadergetmethodfromdocumentposition-method"></a><span data-ttu-id="9413f-103">ISymUnmanagedReader::GetMethodFromDocumentPosition 메서드</span><span class="sxs-lookup"><span data-stu-id="9413f-103">ISymUnmanagedReader::GetMethodFromDocumentPosition Method</span></span>

<span data-ttu-id="9413f-104">문서의 지정 된 위치에 중단점을 포함 하는 메서드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9413f-104">Returns the method that contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9413f-105">구문</span><span class="sxs-lookup"><span data-stu-id="9413f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodFromDocumentPosition (  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32  line,  
    [in]  ULONG32  column,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9413f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9413f-106">Parameters</span></span>  

 `document`  
 <span data-ttu-id="9413f-107">진행 지정 된 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="9413f-107">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="9413f-108">진행 지정 된 문서의 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="9413f-108">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="9413f-109">진행 지정 된 문서의 열입니다.</span><span class="sxs-lookup"><span data-stu-id="9413f-109">[in] The column of the specified document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="9413f-110">제한이 중단점을 포함 하는 메서드를 나타내는 [ISymUnmanagedMethod Interface](isymunmanagedmethod-interface.md) 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9413f-110">[out] A pointer to the address of a [ISymUnmanagedMethod Interface](isymunmanagedmethod-interface.md) object that represents the method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9413f-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="9413f-111">Return Value</span></span>  

 <span data-ttu-id="9413f-112">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="9413f-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9413f-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9413f-113">Requirements</span></span>  

 <span data-ttu-id="9413f-114">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="9413f-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9413f-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9413f-115">See also</span></span>

- [<span data-ttu-id="9413f-116">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9413f-116">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
