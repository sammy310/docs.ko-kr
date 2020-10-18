---
title: 파일이 이미 열려 있습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: ce8f8bf96d7355e45b2df82e8a131472c2ed2367
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162754"
---
# <a name="file-already-open"></a><span data-ttu-id="e5ac2-102">파일이 이미 열려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5ac2-102">File already open</span></span>

<span data-ttu-id="e5ac2-103">경우에 따라 다른 작업을 수행 하거나 다른 작업을 수행 하기 전에 파일을 닫아야 합니다 `FileOpen` .</span><span class="sxs-lookup"><span data-stu-id="e5ac2-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="e5ac2-104">이 오류의 가능한 원인:</span><span class="sxs-lookup"><span data-stu-id="e5ac2-104">Among the possible causes of this error are:</span></span>

- <span data-ttu-id="e5ac2-105">`FileOpen`이미 열려 있는 파일에 대해 순차적 출력 모드 작업이 실행 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e5ac2-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>

- <span data-ttu-id="e5ac2-106">문이 열려 있는 파일을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5ac2-106">A statement refers to an open file.</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="e5ac2-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="e5ac2-107">To correct this error</span></span>

- <span data-ttu-id="e5ac2-108">문을 실행 하기 전에 파일을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="e5ac2-108">Close the file before executing the statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5ac2-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5ac2-109">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
