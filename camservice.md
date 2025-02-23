## サービスの作成

サービスは、非技術者の方むけに、難しい技術情報を隠蔽した上で、環境をシンプルに払い出すための仕組みです。

1. Add Category をクリックして、「AWS環境払出し」というカテゴリを作成します。
1. Create Service をクリックします。ServiceNameに「VM払出し」を指定し、Categoryに先程作成した「AWS環境払出し」カテゴリを指定し、「Create」をクリックします。
1. サービスの定義画面が開きます。通常はテンプレートの時と同様１つずつ開発を行っていきますが、ハンズオンでの作業効率化のため既に定義が行われたソースを読み込みペーストします。
   [定義済みファイル](https://raw.githubusercontent.com/ICpTrial/ICPTrialJapan/master/cam/service/awsvmdeployservice.yaml) をクリックして内容をコピーします。
1. 定義画面の Source Code を選択し、コピーした内容を貼り付け、一旦保管します。 ※ サービスファイル中身一部見直し中
   ![サービスのインポート](https://github.com/ICpTrial/ICPTrialJapan/blob/master/cam/pics/ServiceImport.png)


## インポートしたサービスの確認

1. Overviewタブの確認　
    サービスの説明が記載されています。
      ![サービスの概要](https://github.com/ICpTrial/ICPTrialJapan/blob/master/cam/pics/serviceoverview.png)
1. Parameterタブの確認
    1. Service Parameters
        サービス利用者に指定してもらうパラメータが指定されています。テクニカルに必要な情報だけでなく、利用者氏名やメールアドレス、賦課部門コードなど、ビジネス上必要な情報も指定させることができます。
        また、Instance Sizeでは、t2.nano t2.micro などテクニカルな表現ではなく、梅構成、竹構成、松構成など、ユーザーに分かりやすい表現で指定させています。
      ![サービスのパラメータ](https://github.com/ICpTrial/ICPTrialJapan/blob/master/cam/pics/serviceparameters.png)
       
1. Composition タブの確認
    1. 利用者が指定したパラメータ値と実際に払い出されるテンプレートのワークフローを作成することが可能です
    ここでは InstanceSizeの選択（梅構成、竹構成、松構成）に応じて、Templateに渡される InstanceTypeの値を変えています。
       ![サービスの作成](https://github.com/ICpTrial/ICPTrialJapan/blob/master/cam/pics/servicecomposition.png)
       
1. Plan & Forms 
    1. プランを設定することで、１つの Service Composition の中で、選べるパラメータを制限することが可能です。
    この例では、FREEPLANでは梅構成しか選べないようにしていますが、東京DCプラン、米国DC用プランと分けるなど、１つのService Composition を様々なプランに分けて構成することができます。
       ![サービスのプラン](https://github.com/ICpTrial/ICPTrialJapan/blob/master/cam/pics/serviceplan.png)
      

最後に TerraformテンプレートのGUI開発ツールである BluePrint Designer を見てみましょう [CAMの利用３](https://github.com/ICpTrial/ICPTrialJapan/blob/master/cambpd.md)
       
