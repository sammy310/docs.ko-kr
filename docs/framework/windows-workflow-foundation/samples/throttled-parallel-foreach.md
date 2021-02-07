---
description: '자세히 알아보기: 제한 병렬 ForEach'
title: Throttled Parallel ForEach
ms.date: 03/30/2017
ms.assetid: f2855b5f-e9a7-433d-96a4-40fc31025215
ms.openlocfilehash: 2c1d1386f0b8c5b3c68d60bc83386ccfdf5e7875
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741681"
---
# <a name="throttled-parallel-foreach"></a>Throttled Parallel ForEach

`ThrottleParallelForEach` 활동은 실행할 동시 분기 수를 제한하는 동시 비율을 설정하도록 허용한다는 점만 제외하면 <xref:System.Activities.Statements.ParallelForEach%601> 활동과 비슷합니다. `ThrottleParallelForEach` 활동은 다른 활동(자식 활동)을 예약해야 하고 <xref:System.Activities.NativeActivity> 클래스를 통해서만 액세스 가능하기 때문에 <xref:System.Activities.NativeActivityContext>에서 파생됩니다.

## <a name="projects"></a>프로젝트

|**ProjectName**|**설명**|**기본 파일**|
|-|-|-|
|ThrottledParallelForEach|`ThrottledParallelForEach` 활동과 이 활동의 디자이너가 들어 있습니다.|ThrottledParallelForEach.cs<br /><br /> `ThrottledParallelForEach` 활동 정의입니다.|
|CodeTestClient|명령적 코드를 사용하여 `ThrottledParallelForEach`가 있는 워크플로를 구성 및 실행하는 샘플 클라이언트 애플리케이션입니다.|Program.cs<br /><br /> 샘플 워크플로의 인스턴스를 정의하고 실행합니다.|

## <a name="to-use-this-sample"></a>이 샘플을 사용하려면

1. Visual Studio 2010을 사용 하 여 ThrottledParallelForEach 파일을 엽니다.

2. Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.

3. F5 키를 눌러 솔루션을 실행합니다.

> [!IMPORTANT]
> 컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> 이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다. 이 샘플은 다음 디렉터리에 있습니다.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\ThrottledParallelForEach`
