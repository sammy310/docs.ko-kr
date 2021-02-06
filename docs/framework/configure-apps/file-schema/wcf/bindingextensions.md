---
description: 다음에 대해 자세히 알아보세요. <bindingExtensions>
title: <bindingExtensions>
ms.date: 03/30/2017
ms.assetid: 8373f94d-d095-486f-8f1e-4ac2f72b58c7
ms.openlocfilehash: e568c7dd2da509709e5c85d3181d1808b1c636df
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639408"
---
# \<bindingExtensions>

이 섹션은 시스템 또는 애플리케이션 구성 파일의 사용자 정의 바인딩을 사용할 수 있도록 합니다. `add` 키워드를 사용하고 요소의 `type` 특성을 사용자 정의 바인딩으로 설정하고 `name` 특성을 사용자 정의 바인딩의 이름으로 설정하여 사용자 정의 바인딩을 이 컬렉션에 추가할 수 있습니다.

바인딩 확장을 사용하면 엔드포인트 구성의 일부로 사용할 사용자 정의 바인딩을 만들 수 있습니다. 프로그래밍에서 바인딩 확장은 추상 클래스 <xref:System.ServiceModel.Channels.Binding>을 구현하는 형식입니다.

다음 예제에서는 요소 및 특성을 사용 하 여 `add` `name` `bindingExtensions` 구성 파일의 섹션에 바인딩 확장을 추가 합니다.

```xml
<system.serviceModel>
  <extensions>
    <bindingExtensions>
      <add name="MyBinding"
           type="Microsoft.ServiceModel.Samples.MyBinding, MyBinding,
                 Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />
    </bindingExtensions>
  </extensions>
</system.serviceModel>
```

요소에 구성 기능을 추가하려면 `bindingSection` 요소를 작성하고 등록해야 합니다. 이에 대한 자세한 내용은 <xref:System.Configuration> 설명서를 참조하세요.

요소와 해당 구성 형식을 정의한 후에는 다음 예제와 같이 확장을 끝점의 일부로 사용할 수 있습니다.

```xml
<services>
  <service name="MyService">
    <endpoint address="myAddress"
              binding="MyBinding" />
  </service>
</services>
```

## <a name="see-also"></a>참고 항목

- [바인딩 확장명](../../../wcf/extending/extending-bindings.md)
