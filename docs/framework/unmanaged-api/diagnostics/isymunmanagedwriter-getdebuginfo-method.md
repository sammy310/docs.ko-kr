---
description: '자세히 알아보기: ISymUnmanagedWriter:: GetDebugInfo 메서드'
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
ms.openlocfilehash: 2255cc90c0bfcd36dacdf81703af67d3f47739db
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762320"
---
# <a name="isymunmanagedwritergetdebuginfo-method"></a><span data-ttu-id="770aa-103">ISymUnmanagedWriter::GetDebugInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="770aa-103">ISymUnmanagedWriter::GetDebugInfo Method</span></span>

<span data-ttu-id="770aa-104">컴파일러가 PE (이식 가능한 실행) 파일 헤더에 디버그 디렉터리 항목을 쓰는 데 필요한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="770aa-104">Returns the information necessary for a compiler to write the debug directory entry in the portable executable (PE) file header.</span></span> <span data-ttu-id="770aa-105">기호 작성기는 및를 제외한 모든 필드를 `TimeDateStamp` 채웁니다 `PointerToRawData` .</span><span class="sxs-lookup"><span data-stu-id="770aa-105">The symbol writer fills out all fields except for `TimeDateStamp` and `PointerToRawData`.</span></span> <span data-ttu-id="770aa-106">컴파일러는 이러한 두 필드를 적절 하 게 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="770aa-106">(The compiler is responsible for setting these two fields appropriately.)</span></span>  
  
 <span data-ttu-id="770aa-107">컴파일러는이 메서드를 호출 하 고, 데이터 blob을 PE 파일로 내보내고, `PointerToRawData` IMAGE_DEBUG_DIRECTORY의 필드를 내보낸 데이터를 가리키도록 설정 하 고, IMAGE_DEBUG_DIRECTORY를 pe 파일에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="770aa-107">A compiler should call this method, emit the data blob to the PE file, set the `PointerToRawData` field in the IMAGE_DEBUG_DIRECTORY to point to the emitted data, and write the IMAGE_DEBUG_DIRECTORY to the PE file.</span></span> <span data-ttu-id="770aa-108">또한 컴파일러는 `TimeDateStamp` `TimeDateStamp` 생성 되는 PE 파일의와 같도록 필드를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="770aa-108">The compiler should also set the `TimeDateStamp` field to equal the `TimeDateStamp` of the PE file being generated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="770aa-109">구문</span><span class="sxs-lookup"><span data-stu-id="770aa-109">Syntax</span></span>  
  
```cpp  
HRESULT GetDebugInfo(  
    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,  
    [in]  DWORD cData,  
    [out] DWORD *pcData,  
    [out, size_is(cData),  
        length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="770aa-110">매개 변수</span><span class="sxs-lookup"><span data-stu-id="770aa-110">Parameters</span></span>  

 `pIDD`  
 <span data-ttu-id="770aa-111">[in, out] 기호 작성기가 채울 IMAGE_DEBUG_DIRECTORY에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="770aa-111">[in, out] A pointer to an IMAGE_DEBUG_DIRECTORY that the symbol writer will fill out.</span></span>  
  
 `cData`  
 <span data-ttu-id="770aa-112">진행 `DWORD` 디버그 데이터의 크기를 포함 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="770aa-112">[in] A `DWORD` that contains the size of the debug data.</span></span>  
  
 `pcData`  
 <span data-ttu-id="770aa-113">제한이 `DWORD` 디버그 데이터를 포함 하는 데 필요한 버퍼의 크기를 수신 하는에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="770aa-113">[out] A pointer to a `DWORD` that receives the size of the buffer required to contain the debug data.</span></span>  
  
 `data`  
 <span data-ttu-id="770aa-114">제한이 기호 저장소에 대 한 디버그 데이터를 저장 하기에 충분 한 크기의 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="770aa-114">[out] A pointer to a buffer that is large enough to hold the debug data for the symbol store.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="770aa-115">Return Value</span><span class="sxs-lookup"><span data-stu-id="770aa-115">Return Value</span></span>  

 <span data-ttu-id="770aa-116">메서드가 성공 하면이 고, 그렇지 않으면 S_OK입니다. 그렇지 않으면 E_FAIL 또는 일부 다른 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="770aa-116">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="770aa-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="770aa-117">Requirements</span></span>  

 <span data-ttu-id="770aa-118">**헤더:** CorSym, CorSym</span><span class="sxs-lookup"><span data-stu-id="770aa-118">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="770aa-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="770aa-119">See also</span></span>

- [<span data-ttu-id="770aa-120">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="770aa-120">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
