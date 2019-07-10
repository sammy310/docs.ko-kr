---
title: ISymUnmanagedReader::ReplaceSymbolStore 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.ReplaceSymbolStore
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::ReplaceSymbolStore
helpviewer_keywords:
- ReplaceSymbolStore method [.NET Framework debugging]
- ISymUnmanagedReader::ReplaceSymbolStore method [.NET Framework debugging]
ms.assetid: 43257761-8cb1-4eaf-8fb5-1f3980cb66cd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 525ec4828fb942aeb447940ea68a523cd7c69140
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67736731"
---
# <a name="isymunmanagedreaderreplacesymbolstore-method"></a><span data-ttu-id="55faf-102">ISymUnmanagedReader::ReplaceSymbolStore 메서드</span><span class="sxs-lookup"><span data-stu-id="55faf-102">ISymUnmanagedReader::ReplaceSymbolStore Method</span></span>
<span data-ttu-id="55faf-103">기존 기호 저장소를 델타 기호 저장소로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="55faf-103">Replaces the existing symbol store with a delta symbol store.</span></span> <span data-ttu-id="55faf-104">이 메서드는 비슷합니다는 [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) 메서드를 제외 하 고 지정 된 델타 역할 업데이트 보다 완전 한 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="55faf-104">This method is similar to the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method, except that the given delta acts as a complete replacement rather than an update.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="55faf-105">중 하나만 지정 해야 합니다 `filename` 또는 `pIStream` 매개 변수를 둘 다.</span><span class="sxs-lookup"><span data-stu-id="55faf-105">You need specify only one of the `filename` or `pIStream` parameters, not both.</span></span> <span data-ttu-id="55faf-106">경우 `filename` 를 지정 하면 해당 파일에서 기호를 사용 하 여 기호 저장소 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55faf-106">If `filename` is specified, the symbol store will be updated with the symbols in that file.</span></span> <span data-ttu-id="55faf-107">하는 경우 `pIStream` 를 지정 하면 저장소의 데이터로 업데이트 됩니다는 <xref:System.Runtime.InteropServices.ComTypes.IStream>합니다.</span><span class="sxs-lookup"><span data-stu-id="55faf-107">If `pIStream` is specified, the store will be updated with the data from the <xref:System.Runtime.InteropServices.ComTypes.IStream>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55faf-108">구문</span><span class="sxs-lookup"><span data-stu-id="55faf-108">Syntax</span></span>  
  
```cpp  
HRESULT ReplaceSymbolStore (  
    [in] const WCHAR *filename,  
    [in] IStream *pIStream);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55faf-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="55faf-109">Parameters</span></span>  
 `filename`  
 <span data-ttu-id="55faf-110">[in] 기호 저장소를 포함 하는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="55faf-110">[in] The name of the file containing the symbol store.</span></span>  
  
 `pIStream`  
 <span data-ttu-id="55faf-111">[in] 대 안으로 사용 되는 파일 스트림을 `filename` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="55faf-111">[in] The file stream, used as an alternative to the `filename` parameter.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="55faf-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="55faf-112">Return Value</span></span>  
 <span data-ttu-id="55faf-113">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="55faf-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55faf-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="55faf-114">Requirements</span></span>  
 <span data-ttu-id="55faf-115">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="55faf-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55faf-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="55faf-116">See also</span></span>

- [<span data-ttu-id="55faf-117">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="55faf-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
