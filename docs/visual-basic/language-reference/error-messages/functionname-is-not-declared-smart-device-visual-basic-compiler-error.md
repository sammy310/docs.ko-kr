---
description: "자세한 정보: BC30766: ' <functionname> '이 (가) 선언 되지 않았습니다 (스마트 장치/Visual Basic 컴파일러 오류)."
title: "'<functionname>'이 선언되지 않았습니다(스마트 디바이스-Visual Basic 컴파일러 오류)."
ms.date: 07/20/2015
f1_keywords:
- bc30766
- vbc30766
helpviewer_keywords:
- BC30766
ms.assetid: 13918600-6087-40d7-8134-32aa9d3bfda4
ms.openlocfilehash: 939af146656bc5e5e84b3f0672c730f6a816c043
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796160"
---
# <a name="bc30766-functionname-is-not-declared-smart-devicevisual-basic-compiler-error"></a><span data-ttu-id="7fd88-103">BC30766: ' \<functionname> '이 (가) 선언 되지 않았습니다 (스마트 장치/Visual Basic 컴파일러 오류).</span><span class="sxs-lookup"><span data-stu-id="7fd88-103">BC30766: '\<functionname>' is not declared (Smart Device/Visual Basic Compiler Error)</span></span>

<span data-ttu-id="7fd88-104"><`functionname`> 선언 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="7fd88-104"><`functionname`> is not declared.</span></span> <span data-ttu-id="7fd88-105">파일 I/O 기능은 일반적으로 `Microsoft.VisualBasic` 네임스페이스에서 사용할 수 있지만 대상 버전의 .NET Compact Framework에서 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7fd88-105">File I/O functionality is normally available in the `Microsoft.VisualBasic` namespace, but the targeted version of the .NET Compact Framework does not support it.</span></span>

 <span data-ttu-id="7fd88-106">**오류 ID:** BC30766</span><span class="sxs-lookup"><span data-stu-id="7fd88-106">**Error ID:** BC30766</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="7fd88-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="7fd88-107">To correct this error</span></span>

- <span data-ttu-id="7fd88-108">`System.IO` 네임스페이스에 정의된 함수를 사용하여 파일 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd88-108">Perform file operations with functions defined in the `System.IO` namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="7fd88-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7fd88-109">See also</span></span>

- <xref:System.IO>
- [<span data-ttu-id="7fd88-110">Visual Basic을 사용한 파일 액세스</span><span class="sxs-lookup"><span data-stu-id="7fd88-110">File Access with Visual Basic</span></span>](../../developing-apps/programming/drives-directories-files/file-access.md)
