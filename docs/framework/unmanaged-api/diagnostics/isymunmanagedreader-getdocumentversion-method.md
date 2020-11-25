---
title: ISymUnmanagedReader::GetDocumentVersion 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocumentVersion
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocumentVersion
helpviewer_keywords:
- GetDocumentVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocumentVersion method [.NET Framework debugging]
ms.assetid: a51f1f64-e084-44c5-830c-2222da5a6bbf
topic_type:
- apiref
ms.openlocfilehash: fc38c167b47ea72c7bc7ad81074f9cb1a0d217d8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707570"
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a><span data-ttu-id="c8318-102">ISymUnmanagedReader::GetDocumentVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="c8318-102">ISymUnmanagedReader::GetDocumentVersion Method</span></span>

<span data-ttu-id="c8318-103">지정 된 문서의 지정 된 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c8318-103">Gets the specified version of the specified document.</span></span> <span data-ttu-id="c8318-104">문서 버전은 1부터 시작 하 고 [UpdateSymbolStore](isymunmanagedreader-updatesymbolstore-method.md) 메서드를 사용 하 여 문서가 업데이트 될 때마다 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8318-104">The document version starts at 1 and is incremented each time the document is updated using the [UpdateSymbolStore](isymunmanagedreader-updatesymbolstore-method.md) method.</span></span> <span data-ttu-id="c8318-105">`pbCurrent`매개 변수가 이면 `true` 문서의 최신 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="c8318-105">If the `pbCurrent` parameter is `true`, this is the latest version of the document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8318-106">구문</span><span class="sxs-lookup"><span data-stu-id="c8318-106">Syntax</span></span>  
  
```cpp  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8318-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c8318-107">Parameters</span></span>  

 `pDoc`  
 <span data-ttu-id="c8318-108">진행 지정 된 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="c8318-108">[in] The specified document.</span></span>  
  
 `version`  
 <span data-ttu-id="c8318-109">제한이 지정 된 문서의 버전을 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c8318-109">[out] A pointer to a variable that receives the version of the specified document.</span></span>  
  
 `pbCurrent`  
 <span data-ttu-id="c8318-110">제한이 `true` 최신 버전의 문서 이거나 최신 버전이 아닌 경우를 받는 변수에 대 한 포인터입니다 `false` .</span><span class="sxs-lookup"><span data-stu-id="c8318-110">[out] A pointer to a variable that receives `true` if this is the latest version of the document, or `false` if it isn't the latest version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c8318-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="c8318-111">Return Value</span></span>  

 <span data-ttu-id="c8318-112">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="c8318-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8318-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c8318-113">Requirements</span></span>  

 <span data-ttu-id="c8318-114">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="c8318-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8318-115">참조</span><span class="sxs-lookup"><span data-stu-id="c8318-115">See also</span></span>

- [<span data-ttu-id="c8318-116">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c8318-116">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
