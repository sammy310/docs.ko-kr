---
description: '자세한 정보: 프로그래밍 모델 항목 트리'
title: Programming Model Item Tree
ms.date: 03/30/2017
ms.assetid: 0229efde-19ac-4bdc-a187-c6227a7bd1a5
ms.openlocfilehash: 8dfcab99bb5e32d202fe2bdc09d63d8b7da6e748
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741859"
---
# <a name="programming-model-item-tree"></a>Programming Model Item Tree

이 샘플에서는 <xref:System.Activities.Presentation.Model.ModelItem> Windows Presentation Foundation (WPF) 트리 뷰에서 선언적 데이터 바인딩을 사용 하 여 트리를 탐색 하는 방법을 보여 줍니다.

## <a name="sample-details"></a>샘플 세부 정보

 <xref:System.Activities.Presentation.Model.ModelItem>트리는 Windows 워크플로 디자이너 인프라에서 편집 중인 기본 인스턴스에 대 한 데이터를 노출 하는 데 사용 되는 추상화입니다. 다음 그림은 워크플로 디자이너 내에서 인프라의 다양 한 계층을 묘사 하는 것입니다.

 ![워크플로 디자이너 아키텍처를 보여 주는 다이어그램입니다.](./media/programming-model-item-tree/workflow-designer-architecture.jpg)

 <xref:System.Activities.Presentation.Model.ModelItem>은 내부 값에 대한 포인터와 <xref:System.Activities.Presentation.Model.ModelProperty> 개체의 컬렉션으로 구성됩니다. <xref:System.Activities.Presentation.Model.ModelProperty> 개체는 속성의 이름 및 형식 같은 데이터와 값에 대한 포인터로 구성되며 이 값은 또 다른 <xref:System.Activities.Presentation.Model.ModelItem>입니다. 값 변환기는 <xref:System.Activities.Presentation.Model.ModelItem>에서 반환된 <xref:System.Activities.Presentation.Model.ModelProperty>의 일부를 조작하여 트리 뷰에 올바르게 나타나도록 하는 데 사용됩니다. 그런 다음 샘플에서는 다음 예제에 표시된 것과 같은 명령적 구문을 사용하여 <xref:System.Activities.Presentation.Model.ModelItem> 트리에 대해 명령적으로 프로그래밍하는 방법을 보여 줍니다.

```csharp
ModelItem mi = wd.Context.Services.GetService<ModelService>().Root;
ModelProperty mp = mi.Properties["Activities"];
mp.Collection.Add(new Persist());
ModelItem justAdded = mp.Collection.Last();
justAdded.Properties["DisplayName"].SetValue("new name");
```

#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면

1. Visual Studio 2010에서 ProgrammingModelItemTree 솔루션을 엽니다.

2. **빌드** 메뉴에서 **솔루션 빌드** 를 선택 하 여 솔루션을 빌드합니다.

3. F5 키를 눌러 애플리케이션을 실행합니다. WPF 양식이 표시 됩니다.

4. **WF 로드** 단추를 클릭 하 여를 로드 하 <xref:System.Activities.Presentation.Model.ModelItem> 고 트리 뷰에 바인딩합니다.

5. **모델 항목 트리 변경** 단추를 클릭 하면 이전 코드를 실행 하 여 트리에 항목을 추가 하 고 속성을 설정 합니다.

> [!IMPORTANT]
> 컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다. 이 샘플은 다음 디렉터리에 있습니다.  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ProgrammingModelItemTree`  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Data.IValueConverter>
