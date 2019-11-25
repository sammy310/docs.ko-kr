---
title: 컴퓨터에 대한 정보 가져오기
ms.date: 07/20/2015
helpviewer_keywords:
- My.Computer.Info object [Visual Basic], tasks
ms.assetid: 13c145bc-5c85-4fea-a5dd-2ca8681a0252
ms.openlocfilehash: fd5b49cd053d70e752352e2b050f9202564ee7d7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348116"
---
# <a name="getting-information-about-the-computer-visual-basic"></a><span data-ttu-id="23b19-102">컴퓨터에 대한 정보 가져오기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="23b19-102">Getting Information about the Computer (Visual Basic)</span></span>

<span data-ttu-id="23b19-103">`My.Computer.Info` 개체는 컴퓨터의 메모리, 로드된 어셈블리, 이름 및 운영 체제에 대한 정보를 가져오기 위한 속성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="23b19-103">The `My.Computer.Info` object provides properties for getting information about the computer's memory, loaded assemblies, name, and operating system.</span></span>

## <a name="remarks"></a><span data-ttu-id="23b19-104">설명</span><span class="sxs-lookup"><span data-stu-id="23b19-104">Remarks</span></span>

<span data-ttu-id="23b19-105">이 표에서는 `My.Computer.Info` 개체를 통해 일반적으로 수행되는 작업을 나열하고, 각 작업을 수행하는 방법을 보여 주는 항목을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="23b19-105">This table lists tasks commonly accomplished through the `My.Computer.Info` object and points to topics demonstrating how to perform each.</span></span>

|<span data-ttu-id="23b19-106">대상</span><span class="sxs-lookup"><span data-stu-id="23b19-106">To</span></span>|<span data-ttu-id="23b19-107">참조 항목</span><span class="sxs-lookup"><span data-stu-id="23b19-107">See</span></span>|
|---|---|
|<span data-ttu-id="23b19-108">애플리케이션이 설치되어 있는 컴퓨터에 사용할 수 있는 가상 주소 공간 크기 확인</span><span class="sxs-lookup"><span data-stu-id="23b19-108">Determine how much virtual address space is available for the computer on which the application is installed</span></span>|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.TotalVirtualMemory%2A>|
|<span data-ttu-id="23b19-109">애플리케이션을 실행 중인 컴퓨터의 플랫폼 유형 확인</span><span class="sxs-lookup"><span data-stu-id="23b19-109">Determine the platform type of the computer on which the application is running</span></span>|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSPlatform%2A>|
|<span data-ttu-id="23b19-110">애플리케이션을 실행 중인 컴퓨터의 운영 체제 확인</span><span class="sxs-lookup"><span data-stu-id="23b19-110">Determine the operating system of the computer on which the application is running</span></span>|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName%2A>|
|<span data-ttu-id="23b19-111">애플리케이션을 실행 중인 컴퓨터에 설치된 서비스 팩 확인</span><span class="sxs-lookup"><span data-stu-id="23b19-111">Determine what service packs have been installed on the computer on which the application is running</span></span>|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSVersion%2A>|
|<span data-ttu-id="23b19-112">애플리케이션을 실행 중인 컴퓨터에 설치된 `UICulture` 확인</span><span class="sxs-lookup"><span data-stu-id="23b19-112">Determine the installed `UICulture` on the computer on which the application is running.</span></span>|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.InstalledUICulture%2A>|

## <a name="see-also"></a><span data-ttu-id="23b19-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="23b19-113">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.ServerComputer.Info%2A>
