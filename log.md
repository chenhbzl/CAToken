#####实现

  1. 发币之实现代币的必要的管理，转移。合约简化，安全性高。日后扩展可以用公司系统。

  2. ICO 采用各个账户收币，合约不负责自动发币，可以后台发起流程。

     考虑到接受以太币和比特币还有法币 都需要接受ICO的资金  为了统一性，可以用不同账号接受币接受完毕后，人工审核后，发币给相应的客户，而不要用contracts方式发币//

  3. 员工管理不写在合约里面，如果写在合约里面比较复杂，浪费燃料。

  4. 关于锁定的想法，代币可以限制小金额交易的日期期限，以及大金额交易日期期限。暂时没有做单独账户限制。

#####网站部分#####
 
  1. 需要收币
     各种货币管理表，以及汇率，收币账号
  2. 退币
     内网一个收退币地址，验证退币，退发fiat
  3. 需要和交易所关联你的币，客户才方便查询。

#####合约部分#####：

  #VarPublic
    
    1. 默认ERC2.0的变量
    
    2. 保证金池总量（所有者可编辑保证金变量设置着） reserve fund

    3. 保证金使用量（已发出代币） 

  #Account address

    1. owner

      不持有币

    2. smalldistributor

      少量币颁发账号，可以设置颁发总量，以及单次最大量。

    3. largedistributor

      大量币颁发账号，可以设置颁发总量，以及单次最大量。

    4. reservefundeditor

      调整保证金的总量账户，增加，owner持币增加，减少owner持币减少，但是不得


  #程序定义
  
    1. changeowner，and set employee 
      所有者可以修改所有者,设置一些职员等

    2. setdistributor and limitations 
      设置账户的最大操作金额，以及单次最大操作金额。

    3. transfer 
      转账只有转账人可以转

    4. setreserve
      调整保证金的总量账户，增加，owner持币增加，减少owner持币减少，但是已发行数量不的少于总量。
      
    5. burn 放弃自己的代币//实际释放的代币会收回