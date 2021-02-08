---
description: '자세히 알아보기: 파일이 이미 열려 있습니다.'
title: 파일이 이미 열려 있습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 2f3345c15f4a3095a8e733c2c8424edb25b4dee6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796303"
---
# <a name="file-already-open"></a><span data-ttu-id="b7e15-103">파일이 이미 열려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7e15-103">File already open</span></span>

<span data-ttu-id="b7e15-104">경우에 따라 다른 작업을 수행 하거나 다른 작업을 수행 하기 전에 파일을 닫아야 합니다 `FileOpen` .</span><span class="sxs-lookup"><span data-stu-id="b7e15-104">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="b7e15-105">이 오류의 가능한 원인:</span><span class="sxs-lookup"><span data-stu-id="b7e15-105">Among the possible causes of this error are:</span></span>

- <span data-ttu-id="b7e15-106">`FileOpen`이미 열려 있는 파일에 대해 순차적 출력 모드 작업이 실행 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b7e15-106">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>

- <span data-ttu-id="b7e15-107">문이 열려 있는 파일을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7e15-107">A statement refers to an open file.</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="b7e15-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="b7e15-108">To correct this error</span></span>

- <span data-ttu-id="b7e15-109">문을 실행 하기 전에 파일을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="b7e15-109">Close the file before executing the statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7e15-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7e15-110">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
