---
title: Programming Model Item Tree
ms.date: 03/30/2017
ms.assetid: 0229efde-19ac-4bdc-a187-c6227a7bd1a5
ms.openlocfilehash: f3def07ecbc60362b2a8c1d38689dc686cd5bbd5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59086470"
---
# <a name="programming-model-item-tree"></a>Programming Model Item Tree
이 샘플을 탐색 하는 방법을 보여 줍니다는 <xref:System.Activities.Presentation.Model.ModelItem> Windows Presentation Foundation (WPF) 트리 뷰에서 선언적 데이터 바인딩을 사용 하 여 트리.

## <a name="sample-details"></a>샘플 세부 정보
 <xref:System.Activities.Presentation.Model.ModelItem> 트리는 [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] 인프라에서 편집할 기본 인스턴스에 대한 데이터를 노출하는 데 사용되는 추상화입니다. 다음 그림에서는 [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] 내의 다양한 인프라 계층을 보여 줍니다.

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

1.  Visual Studio 2010에서 ProgrammingModelItemTree.sln 솔루션을 엽니다.

2.  선택 하 여 솔루션을 빌드합니다 **솔루션 빌드** 에서 합니다 **빌드** 메뉴.

3.  F5 키를 눌러 애플리케이션을 실행합니다. 그러면 [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] 폼이 표시됩니다.

4.  클릭 합니다 **WF 로드** 로드 하려면 단추를 <xref:System.Activities.Presentation.Model.ModelItem> 트리 뷰에 바인딩합니다.

5.  클릭 하는 **변경 모델 항목 트리** 단추 트리로 항목을 추가 하 고 속성 설정 앞의 코드를 실행 합니다.

> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4 용 Windows WF (Workflow Foundation) 샘플](https://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ProgrammingModelItemTree`  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Data.IValueConverter>
