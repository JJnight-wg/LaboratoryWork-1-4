# LaboratoryWork-1-4
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace WpfApp1.Model
{
    class Employee
    {
        public int Id { get; set; }
        public string LastName { get; set; }
        public string FirstName { get; set; }
        public string SecondName { get; set; }
        public string Title { get; set; }
        public DateTime BirthDay { get; set; }
        public string Address { get; set; }
        public string City { get; set; }
        public string Region { get; set; }
        public long Phone { get; set; }
        public string Email { get; set; }



        public Employee() { }
        public Employee(int id, string lastName, string firstName, string secondName, string  title, DateTime birthDay, string address, string city, string region, long phone, string email )
        {
            this.Id = id;
            this.LastName = lastName;
            this.FirstName = firstName;
            this.SecondName = secondName;
            this.Title = title;
            this.BirthDay = birthDay;
            this.City = city;
            this.Region = region;
            this.Phone = phone;
            this.Email = email;


        }

    }
}



     class EmployeeTerritory
    {
        public int Id { get; set; }
        public int EmployeeId { get; set; }
        public int TerritoryId { get; set; }



        public EmployeeTerritory() { }
        public EmployeeTerritory(int id, int employeeId, int territoryId)
        {
            this.Id = id;
            this.EmployeeId = employeeId;
            this.TerritoryId = territoryId;

        }
    }
}





     class Region
    {
        public int Id { get; set; }
        public string RegionDisription { get; set; }


        public Region() { }
        public Region(int id, string regionDisription)
        {
            this.Id = id;
            this.RegionDisription = regionDisription;

        }
    }
}




     class Territory
    {
        public int Id { get; set; }
        public int RegionId { get; set; }
        public string Discripsion { get; set; }



        public Territory() { }
        public Territory(int id, int regionId, string discripsion)
        {
            this.Id = id;
            this.RegionId = regionId;
            this.Discripsion = discripsion;

        }
    }
}

XMAIL

<Window x:Class="WpfApp1.View.WindowEmployee"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:WpfApp1.View"
        mc:Ignorable="d"
        Title="Сотрудники" Height="450" Width="700">
    <Grid>
        <Grid.ColumnDefinitions>
            <ColumnDefinition/>
        </Grid.ColumnDefinitions>
        <Menu>
            <StackPanel>
                <ListView x:Name="lvEmployee" RenderTransformOrigin="0.55,0.493" Width="695">
                    <ListView.View>
                        <GridView>
                            <GridView.Columns>
                                <GridViewColumn Header="Код" Width="80" 
                                    DisplayMemberBinding="{Binding Id}"/>
                                <GridViewColumn Header="Фамилия" Width="100"
                                    DisplayMemberBinding="{Binding LastName}"/>
                                <GridViewColumn Header="Имя" Width="90"
                                     DisplayMemberBinding="{Binding FirstName}"/>
                                <GridViewColumn Header="Отчество" Width="100"
                                     DisplayMemberBinding="{Binding SecondName}"/>
                                <GridViewColumn Header="Должность" Width="130"
                                     DisplayMemberBinding="{Binding Title}"/>
                                <GridViewColumn Header="Дата рождения" Width="100"
                                    DisplayMemberBinding="{Binding BirthDay}"/>
                                  


                            </GridView.Columns>
                        </GridView>
                    </ListView.View>
                </ListView>

            </StackPanel>

        </Menu>
    </Grid>
</Window>

<Window x:Class="WpfApp1.View.WindowEmployeeTerritory"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:WpfApp1.View"
        mc:Ignorable="d"
        Title="Сотрудники городов" Height="450" Width="442">
    <Grid>
        <Menu/>
        <StackPanel Background="#FFD8D8D8">
            <Label Margin="5" HorizontalAlignment="Center">Список сотрудников городов</Label>
            <ListView x:Name="lvEmployeeTerritory" Background="#FFD3CDCD">
                <ListView.View >
                    <GridView>
                        <GridView.Columns>
                            <GridViewColumn Header="Код должности" Width="100"
 DisplayMemberBinding="{Binding EmployeeId}"/>
                            <GridViewColumn Header="Код города"
 DisplayMemberBinding="{Binding TerritoryId}"/>
                        </GridView.Columns>
                    </GridView>
                </ListView.View>
            </ListView>
        </StackPanel>

    </Grid>
</Window>


<Window x:Class="WpfApp1.View.WindowRegion"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:WpfApp1.View"
        mc:Ignorable="d"
        Title="Область" Height="450" Width="410">
    <StackPanel Background="#FFD8D8D8">
        <Label Margin="5" HorizontalAlignment="Center">Список областей</Label>
        <ListView x:Name="lvRegion" Background="#FFD3CDCD">
            <ListView.View >
                <GridView>
                    <GridView.Columns>
                        <GridViewColumn Header="Код" Width="50"
 DisplayMemberBinding="{Binding Id}"/>
                        <GridViewColumn Header="Наименование областей"
 DisplayMemberBinding="{Binding RegionDisription}"/>
                    </GridView.Columns>
                </GridView>
            </ListView.View>
        </ListView>
    </StackPanel>
</Window>

 <Grid>
 <Grid.RowDefinitions>
 <RowDefinition Height="40*"/>
 <RowDefinition Height="40*"/>
 <RowDefinition Height="40*"/>
 </Grid.RowDefinitions>
 <Grid.ColumnDefinitions>
 <ColumnDefinition Width="40*"/>
 <ColumnDefinition Width="75*"/>
 </Grid.ColumnDefinitions>
 <TextBlock Grid.Row="0" Grid.Column="0" Text="Код:"
 HorizontalAlignment="Right" VerticalAlignment="Center" Margin="5"/>
 <TextBlock Grid.Row="1" Grid.Column="0" Text="Должность:"
 HorizontalAlignment="Right" VerticalAlignment="Center" Margin="5"/>
 <TextBox x:Name="TbId" Grid.Row="0" Grid.Column="1" Height="20" Width="50"
 HorizontalAlignment="Left" VerticalAlignment="Center" Margin="5"
 Text="{Binding Id}" IsEnabled="False"/>
 <TextBox x:Name="TbRole" Grid.Row="1" Grid.Column="1" Height="20" Width="130"
 HorizontalAlignment="Left" VerticalAlignment="Center" Margin="5"
 Text="{Binding NameRole}"/>
 <StackPanel Grid.Column="0" Grid.ColumnSpan="2" Grid.Row="2"
 Orientation="Horizontal" HorizontalAlignment="Right">
 <Button x:Name="BtSave" Content="Сохранить" Height="25"
 HorizontalAlignment="Right" VerticalAlignment="Top"
 Margin="5,10,10,5" IsDefault="True" Click="BtSave_Click"/>
 <Button x:Name="BtCansel" Content="Отменить" Height="25"
 HorizontalAlignment="Right" VerticalAlignment="Top"
 Margin="5,10,10,5" IsCancel="True"/>
 </StackPanel>
 </Grid>
</Window>
