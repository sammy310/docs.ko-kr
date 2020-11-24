---
title: ISymUnmanagedReader::GetMethodsFromDocumentPosition 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetMethodsFromDocumentPosition
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetMethodsFromDocumentPosition
helpviewer_keywords:
- GetMethodsFromDocumentPosition method [.NET Framework debugging]
- ISymUnmanagedReader::GetMethodsFromDocumentPosition method [.NET Framework debugging]
ms.assetid: 83605f1e-e4f3-49e6-859b-f13cad68bb54
topic_type:
- apiref
ms.openlocfilehash: 5298dd0f53693d96b748f6c839660838fdfad4ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689552"
---
# <a name="isymunmanagedreadergetmethodsfromdocumentposition-method"></a><span data-ttu-id="b9399-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition 메서드</span><span class="sxs-lookup"><span data-stu-id="b9399-102">ISymUnmanagedReader::GetMethodsFromDocumentPosition Method</span></span>

<span data-ttu-id="b9399-103">각각 문서의 지정 된 위치에 중단점을 포함 하는 메서드의 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9399-103">Returns an array of methods, each of which contains the breakpoint at the given position in a document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9399-104">구문</span><span class="sxs-lookup"><span data-stu-id="b9399-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodsFromDocumentPosition (  
    [in]  ISymUnmanagedDocument* document,  
    [in]  ULONG32 line,  
    [in]  ULONG32 column,  
    [in]  ULONG32 cMethod,  
    [out] ULONG32* pcMethod,  
    [out, size_is (cMethod),  
        length_is (*pcMethod)] ISymUnmanagedMethod* pRetVal[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9399-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b9399-105">Parameters</span></span>  

 `document`  
 <span data-ttu-id="b9399-106">진행 지정 된 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="b9399-106">[in] The specified document.</span></span>  
  
 `line`  
 <span data-ttu-id="b9399-107">진행 지정 된 문서의 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="b9399-107">[in] The line of the specified document.</span></span>  
  
 `column`  
 <span data-ttu-id="b9399-108">진행 지정 된 문서의 열입니다.</span><span class="sxs-lookup"><span data-stu-id="b9399-108">[in] The column of the specified document.</span></span>  
  
 `cMethod`  
 <span data-ttu-id="b9399-109">[in] `pRetVal` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="b9399-109">[in] The size of the `pRetVal` array.</span></span>  
  
 `pcMethod`  
 <span data-ttu-id="b9399-110">제한이 배열에 반환 된 요소의 수를 받는 변수에 대 한 포인터 `pRetVal` 입니다.</span><span class="sxs-lookup"><span data-stu-id="b9399-110">[out] A pointer to a variable that receives the number of elements returned in the `pRetVal` array.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="b9399-111">제한이 각각 중단점을 포함 하는 메서드를 나타내는 [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) 개체를 가리키는 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="b9399-111">[out] An array of pointers, each of which points to an [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) object that represents a method containing the breakpoint.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9399-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="b9399-112">Return Value</span></span>  

 <span data-ttu-id="b9399-113">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="b9399-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9399-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b9399-114">Requirements</span></span>  

 <span data-ttu-id="b9399-115">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="b9399-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9399-116">참조</span><span class="sxs-lookup"><span data-stu-id="b9399-116">See also</span></span>

- [<span data-ttu-id="b9399-117">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b9399-117">ISymUnmanagedReader Interface</span></span>](isymunmanagedreader-interface.md)
