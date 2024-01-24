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


