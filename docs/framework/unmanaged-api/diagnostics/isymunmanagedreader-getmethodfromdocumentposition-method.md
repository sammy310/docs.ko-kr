---
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
ms.openlocfilehash: 417644e5d0c7af802d5266bd1825efa83c181597
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689604"
---
# <a name="isymunmanagedreadergetmethodfromdocumentposition-method"></a><span data-ttu-id="e0780-102">ISymUnmanagedReader::GetMethodFromDocumentPosition 메서드</span><span class="sxs-lookup"><span data-stu-id="e0780-102">ISymUnmanagedReader::GetMethodFromDocumentPosition Method</span></span>

<span data-ttu-id="e0780-103">문서의 지정 된 위치에 중단점을 포함 하는 메서드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0780-103">Returns the method that contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0780-104">구문</span><span class="sxs-lookup"><span data-stu-id="e0780-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodFromDocumentPosition (  
    [in]  ISymUnmanagedDocument*  document,  
    [in]  ULONG32  line,  
    [in]  ULONG32  column,  
    [out, retval] ISymUnmanagedMethod**  pRetVal);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0780-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e0780-105">Parameters</span></span>  

 `document`  
 <span data-ttu-id="e0780-106">진행 지정 된 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="e0780-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="e0780-107">진행 지정 된 문서의 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="e0780-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="e0780-108">진행 지정 된 문서의 열입니다.</span><span class="sxs-lookup"><span data-stu-id="e0780-108">[in] The column of the specified document.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="e0780-109">제한이 중단점을 포함 하는 메서드를 나타내는 [ISymUnmanagedMethod Interface](isymunmanagedmethod-interface.md) 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e0780-109">[out] A pointer to the address of a [ISymUnmanagedMethod Interface](isymunmanagedmethod-interface.md) object that represents the method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0780-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="e0780-110">Return Value</span></span>  

 <span data-ttu-id="e0780-111">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="e0780-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0780-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e0780-112">Requirements</span></span>  

 <span data-ttu-id="e0780-113">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="e0780-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0780-114">참조</span><span class="sxs-lookup"><span data-stu-id="e0780-114">See also</span></span>

- [<span data-ttu-id="e0780-115">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e0780-115">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
