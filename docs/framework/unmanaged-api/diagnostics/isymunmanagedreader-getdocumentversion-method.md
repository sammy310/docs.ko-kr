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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 92353cfc2d9ce39074bf43937b5673ff51e34822
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939427"
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a><span data-ttu-id="11564-102">ISymUnmanagedReader::GetDocumentVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="11564-102">ISymUnmanagedReader::GetDocumentVersion Method</span></span>
<span data-ttu-id="11564-103">지정 된 문서의 지정 된 버전을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="11564-103">Gets the specified version of the specified document.</span></span> <span data-ttu-id="11564-104">문서 버전 1에서 시작 하 고 문서를 사용 하 여 업데이트 될 때마다 증가 합니다 [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="11564-104">The document version starts at 1 and is incremented each time the document is updated using the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method.</span></span> <span data-ttu-id="11564-105">경우는 `pbCurrent` 매개 변수는 `true`, 문서의 최신 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="11564-105">If the `pbCurrent` parameter is `true`, this is the latest version of the document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11564-106">구문</span><span class="sxs-lookup"><span data-stu-id="11564-106">Syntax</span></span>  
  
```  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11564-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="11564-107">Parameters</span></span>  
 `pDoc`  
 <span data-ttu-id="11564-108">[in] 지정 된 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="11564-108">[in] The specified document.</span></span>  
  
 `version`  
 <span data-ttu-id="11564-109">[out] 지정 된 문서 버전을 수신 하는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="11564-109">[out] A pointer to a variable that receives the version of the specified document.</span></span>  
  
 `pbCurrent`  
 <span data-ttu-id="11564-110">[out] 수신 하는 변수에 대 한 포인터 `true` 경우이 문서의 최신 버전 또는 `false` 최신 버전이 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="11564-110">[out] A pointer to a variable that receives `true` if this is the latest version of the document, or `false` if it isn't the latest version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="11564-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="11564-111">Return Value</span></span>  
 <span data-ttu-id="11564-112">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="11564-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11564-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="11564-113">Requirements</span></span>  
 <span data-ttu-id="11564-114">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="11564-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11564-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="11564-115">See also</span></span>

- [<span data-ttu-id="11564-116">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="11564-116">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
