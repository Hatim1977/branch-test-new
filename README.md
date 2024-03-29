import time
import pandas as pd
import numpy as np

CITY_DATA = { 'chicago': 'chicago.csv',
              'new york city': 'new_york_city.csv',
              'washington': 'washington.csv' }
cities={'chicago','new york city','washington'}
months = {'january','february','march','april','may','june'}
days = {'monday','tuesday','wednesday','thursday','friday''saturday','sunday'}

def get_filters():
    """
    Asks user to specify a city, month, and day to analyze.

    Returns:
        (str) city - name of the city to analyze
        (str) month - name of the month to filter by, or "all" to apply no month filter
        (str) day - name of the day of week to filter by, or "all" to apply no day filter
    """
    print('Hello! Let\'s explore some US bikeshare data!')
    # TO DO: get user input for city (chicago, new york city, washington). HINT: Use a while loop to handle invalid inputs
    while True:
        city = input ("select city from chicago,new york city or washington  :").lower()
        
        if city in cities:
            
            break
        else:
            print("fals")
            
            


    # TO DO: get user input for month (all, january, february, ... , june)
    while True:
        month = input ("select month from january,february,march,april, may or june :").lower()
        if month in months:
            break
        else:
            print("fals")
    

    # TO DO: get user input for day of week (all, monday, tuesday, ... sunday)
    while True:
        day = input ("select day from monday,tuesday,wednesday,thursday,friday ,saturday or sunday :").lower()
        if day in days:
            break
        else:
            print("fals")

    print('-'*40)
    

   
    return city, month, day


#

def load_data(city, month, day):
    """
    Loads data for the specified city and filters by month and day if applicable.

    Args:
        (str) city - name of the city to analyze
        (str) month - name of the month to filter by, or "all" to apply no month filter
        (str) day - name of the day of week to filter by, or "all" to apply no day filter
    Returns:
        df - Pandas DataFrame containing city data filtered by month and day
    """


    return df


def time_stats(df):
    """Displays statistics on the most frequent times of travel."""

    print('\nCalculating The Most Frequent Times of Travel...\n')
    start_time = time.time()

    # TO DO: display the most common month
    most_common_month=df["month"].mode()[0]
    print("the most common month is :".format(most_common_month))


    # TO DO: display the most common day of week
    most_common_day_of_week=df["the most common day of week"].mode90[0]
    print("the most common day of week is :".format(most_common_day_of_week))

    # TO DO: display the most common start hour

    the_most_common_start_hour=df['start time'].dt.hour.mode()[0]
    print("the most common start hour is {} " .format(the_most_common_start_hour))
         
    
      


    print("\nThis took %s seconds." % (time.time() - start_time))
    print('-'*40)


def station_stats(df):
    """Displays statistics on the most popular stations and trip."""

    print('\nCalculating The Most Popular Stations and Trip...\n')
    start_time = time.time()

    # TO DO: display most commonly used start station
    most_commonly_used_start_station=df["start station"].mode()[0]
    print("the most commonly used start station is ".format(most_commonly_used_start_station))

    # TO DO: display most commonly used end station
    most_commonly_used_end_station=df["end station"].mode()[0]
    print("most commonly used end station is ".format(most_commonly_used_end_station))


    # TO DO: display most frequent combination of start station and end station trip
    most_frequent_combination_of_start_station_and_end_station=df[["start station","end station"]].mode().loc[0]
    print("most frequent combination of start station and end station trip is ".format(        most_frequent_combination_of_start_station_and_end_station)
          
    print("\nThis took %s seconds." % (time.time() - start_time))
    print('-'*40)


def trip_duration_stats(df):
    """Displays statistics on the total and average trip duration."""

    print('\nCalculating Trip Duration...\n')
    start_time = time.time()

    # TO DO: display total travel time
          total_travel_time=df["Trip Duration"].sum()
          print("total travel time is :".format(total_travel_time)


    # TO DO: display mean travel time
                mean_travel_time=df["Trip Duration"]mean()
                print("the mean travel time is :".format(mean_travel_time)
                      


    print("\nThis took %s seconds." % (time.time() - start_time))
    print('-'*40)


def user_stats(df):
    """Displays statistics on bikeshare users."""

    print('\nCalculating User Stats...\n')
    start_time = time.time()

    # TO DO: Display counts of user types
     counts_of_user_types=df["User Type"].value_counts()
                      print("the counts of user types is :".format(counts_of_user_types)
                      


    # TO DO: Display counts of gender
                            counts_of_gender=df["Gender"].value_counts()
                            print("the counts of gender is :")
                            print(counts_of_gender)
                            except keyError:
                            print("fals")
                            


    # TO DO: Display earliest, most recent, and most common year of birth
                            earliest_year_of_birth=df["Birth Year"].min()
                            most_recent_year_of_birth=df["Birth Year"].max()
                            most_common_year_of_birth=df["Birth Year"].mod()[0]
                            print(" the year of birth is:".format(earliest_year_of_birth,most_recent_year_of_birth,most_common_year_of_birth)
                                  except keyError:
                                  print("fals")
                                  


    print("\nThis took %s seconds." % (time.time() - start_time))
    print('-'*40)


def main():
    while True:
        city, month, day = get_filters()
        df = load_data(city, month, day)

        time_stats(df)
        station_stats(df)
        trip_duration_stats(df)
        user_stats(df)

        restart = input('\nWould you like to restart? Enter yes or no.\n')
        if restart.lower() != 'yes':
            break


if __name__ == "__main__":
	main()
