class LifeOn6001(object):
    '''Little algoritm based on the life of a student taking
    MIT 6.0.0.1X.  
    name = string with first / last name or nickname
    age= integer
    coffeeIntake = integer with the average cups of coffee per day
    hourSleep= integer with average daily hours of sleep'''
    
    def __init__(self, name, age, coffeeIntake, hourSleep):
        self.name = name
        self.age = age
        self.coffeeIntake = coffeeIntake
        self.hourSleep = hourSleep
        self.grades = {'P1': 0,'P2': 0,'P3': 0,'P4': 0,
                       'P5': 0, 'P6': 0, 'Mid':0, 'Final':0, 'SumFingEx':0}
    
    def getName(self):
        return self.name + ' is a MIT 6.0.0.1X student.'
    
    def getAge(self):
        return self.age
    
    def crazynessLevel(self):
        '''returns level of sanity based on assigments taken'''
        if self.coffeeIntake > 10 and self.hourSleep < 1:
            return 'Status: '+ self.name + ' looks like a zombie on crack.'
        elif self.coffeeIntake > 8:
            return 'Status: '+ self.name + ' iiissss sshhakinng. Gotttta pput dddown the coffee'
        elif self.hourSleep < 1:
            return getHourSleep()
        else:
            return 'Status: '+ self.name + 'is a happy and functional student'
    
    def getCoffeeIntake(self):
        return self.name + ' drinks '+ str(self.coffeeIntake) + ' cups of coffe a day.'
    
    def getHourSleep(self):
        if self.hourSleep > 4:
            return self.name + ' happily sleeps '+ str(self.hourSleep) + ' hours a day.'
        elif self.hourSleep > 1:
            return self.name + ' is super cranky because '+ \
            self.name + ' sleeps '+ str(self.hourSleep) + ' hours a day. '
        else:
            return 'No sleep at all. ' + self.name + ' has turned into a zombie.'
    
    def insertGrade(self, assign, grade ):
        '''Insert grades to gradebook as you finish the assignments
        grade = integer
        assign = string Problem Set (P1,P2, p3...), Midterm (Mid), Final (Final)
        or the sum of points of the finger exercises (SumFingEx)
        '''
        for a, g in self.grades.items():
            if assign in a:
                #assignments take away hours of sleep
                self.hourSleep -= 1
                #assigments increase coffee consumption
                self.coffeeIntake += 1
                if a == 'P4' or a == 'P5':
                    self.hourSleep -= 1
                    self.coffeeIntake += 1
                if a == 'Mid' or a == 'Final':
                    self.hourSleep -= 2
                    self.coffeeIntake += 2
                self.grades[a]= grade
                return a + '= ' + str(grade)
        return 'Assignment not found'
    
    def getGrade(self, assign):
        ''' returns grades of an assignment.
        assign = string containing code for assigment. '''
        for a, g in self.grades.items():
            if assign in a:
                return a + ' = '+ str(g)
        else:
            return 'Assignment not found'
    
    def getCertificate(self):
        total = []
        for a, g in self.grades.items():
            total.append(g)
        if sum(total) > 452:
            return 'A-wesome! '+ self.name + ' is a genius. Give him/ her a certificate and a job at Google'
        elif sum(total) > 377:
            return self.name + ' got a B and a shiny MITx certificate. Congratulations'
        elif sum(total) > 326:
            return self.name + ' barely made it with a C'
        else:
            return 'Failed! '+ self.name + ' should consider something easier like a Microsoft Office course'
        
    def gradeBook(self):
        '''Prints the grades and its percentages'''
        #Max points for each assignment
        self.total = {'P1': 35,'P2': 45,'P3': 45,'P4': 85,
                       'P5': 55, 'P6': 28, 'Mid':105, 'Final':95, 'SumFingEx':50}
        #Print Gradebook
        print( self.getCertificate() + '\n')
        for a, g in self.grades.items():
            print (a + '= ' + str(g) + ' / ' + str(self.total[a]) \
                   + ' / ' + str(int((g / self.total[a])*100)) + '%')
    
    def getSleep(self, hours):
        ''' Getting some sleep improves/ increases daily average, therefore improving the crazyness level
        hours = integer of hours of sleep'''
        self.hourSleep += hours
        return self.name + ' have a daily average of ' + str(self.hourSleep) +' hours of sleep. ' + self.getHourSleep() 
                   
    def __str__(self):
        return self.name + ', ' + str(self.age) + ' years old ' \
        ', drinks '+ str(self.coffeeIntake) + \
        ' cups of coffee daily.  '+ self.getHourSleep()
        
