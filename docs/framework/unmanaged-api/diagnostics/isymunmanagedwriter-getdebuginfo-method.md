---
title: ISymUnmanagedWriter::GetDebugInfo 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.GetDebugInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::GetDebugInfo
helpviewer_keywords:
- ISymUnmanagedWriter::GetDebugInfo method [.NET Framework debugging]
- GetDebugInfo method [.NET Framework debugging]
ms.assetid: dd31c210-6829-45eb-927e-cc53932638b7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8737885015055994bff3f6066bccb551f19f74f4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777314"
---
# <a name="isymunmanagedwritergetdebuginfo-method"></a><span data-ttu-id="aaa4a-102">ISymUnmanagedWriter::GetDebugInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="aaa4a-102">ISymUnmanagedWriter::GetDebugInfo Method</span></span>
<span data-ttu-id="aaa4a-103">컴파일러가 이식 가능한 실행 파일 (PE) 파일 헤더의 디버그 디렉터리 항목을 작성 하는 데 필요한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa4a-103">Returns the information necessary for a compiler to write the debug directory entry in the portable executable (PE) file header.</span></span> <span data-ttu-id="aaa4a-104">기호 작성기를 제외한 모든 필드를 채워 `TimeDateStamp` 고 `PointerToRawData`입니다.</span><span class="sxs-lookup"><span data-stu-id="aaa4a-104">The symbol writer fills out all fields except for `TimeDateStamp` and `PointerToRawData`.</span></span> <span data-ttu-id="aaa4a-105">(컴파일러는 이러한 두 필드를 적절 하 게 설정 하는 일을 담당 합니다.)</span><span class="sxs-lookup"><span data-stu-id="aaa4a-105">(The compiler is responsible for setting these two fields appropriately.)</span></span>  
  
 <span data-ttu-id="aaa4a-106">컴파일러는이 메서드를 호출, PE 파일에 데이터 blob을 내보낼, 설정 된 `PointerToRawData` 내보낸 데이터를 가리키고는 IMAGE_DEBUG_DIRECTORY PE 파일에 쓸 IMAGE_DEBUG_DIRECTORY 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="aaa4a-106">A compiler should call this method, emit the data blob to the PE file, set the `PointerToRawData` field in the IMAGE_DEBUG_DIRECTORY to point to the emitted data, and write the IMAGE_DEBUG_DIRECTORY to the PE file.</span></span> <span data-ttu-id="aaa4a-107">컴파일러 설정 해야 합니다 `TimeDateStamp` 과 동일 하 게 필드는 `TimeDateStamp` 생성 되는 PE 파일의 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa4a-107">The compiler should also set the `TimeDateStamp` field to equal the `TimeDateStamp` of the PE file being generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aaa4a-108">구문</span><span class="sxs-lookup"><span data-stu-id="aaa4a-108">Syntax</span></span>  
  
```cpp  
HRESULT GetDebugInfo(  
    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,  
    [in]  DWORD cData,  
    [out] DWORD *pcData,  
    [out, size_is(cData),  
        length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aaa4a-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="aaa4a-109">Parameters</span></span>  
 `pIDD`  
 <span data-ttu-id="aaa4a-110">[out에서] 기호 작성기가 데이터를 입력 하는 IMAGE_DEBUG_DIRECTORY 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="aaa4a-110">[in, out] A pointer to an IMAGE_DEBUG_DIRECTORY that the symbol writer will fill out.</span></span>  
  
 `cData`  
 <span data-ttu-id="aaa4a-111">[in] `DWORD` 디버그 데이터의 크기를 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa4a-111">[in] A `DWORD` that contains the size of the debug data.</span></span>  
  
 `pcData`  
 <span data-ttu-id="aaa4a-112">[out] 에 대 한 포인터를 `DWORD` 디버그 데이터를 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="aaa4a-112">[out] A pointer to a `DWORD` that receives the size of the buffer required to contain the debug data.</span></span>  
  
 `data`  
 <span data-ttu-id="aaa4a-113">[out] 기호 저장소에 대 한 디버그 데이터를 저장할 수 있도록 충분히 큰 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="aaa4a-113">[out] A pointer to a buffer that is large enough to hold the debug data for the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aaa4a-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="aaa4a-114">Return Value</span></span>  
 <span data-ttu-id="aaa4a-115">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="aaa4a-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aaa4a-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aaa4a-116">Requirements</span></span>  
 <span data-ttu-id="aaa4a-117">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="aaa4a-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aaa4a-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="aaa4a-118">See also</span></span>

- [<span data-ttu-id="aaa4a-119">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aaa4a-119">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
